# Session: Switch to Base32 and the Handling of CIDv0

- **Proposed by:** @kevina
- **Led by:** possibly @kevina
- **Duration:** 30 - 90 minutes, however long it takes to consider the issue carefully.
- **Who has to be there in order for it to work:** @whyrusleeping @diasdavid @Stebalien (maybe @jbenet)

## Overview

Issue "Make base32 CIDv1 the default for go-ipfs is stalled" (https://github.com/ipfs/go-ipfs/issues/4143) in go-ipfs is stalled.  I am not sure the reason but I think part of it is the how to handle CIDv0 (https://github.com/ipfs/go-cid/issues/34).

Having all key players in the same room would be an ideal opportunity to move this forward and work though and outstanding issues.

## Goals

Make decisions on if we want to switch to base32 and CIDv0 will be handled after the switch.

## Key Decisions That Need to Be Made

1. What Base32 encoding to use.

2. Do we want to forbid CidV0 from having a multihash prefix?

3. How will working with CIDv0 links in existing objects be handled?  Part of this answer depends on (2).

4. Do we want to switch the blockstore to work with bare multihashes?

4.1 If yes how will we distinguish between bare multihash and CidV0?  For example when displaying the list of local references.

----


Notes from Deep Dive (hackpad):

# Move to CIDv1 in Base32 (Deep Dive, Berlin 2018) 

```
<cidv1> ::= <multibase-prefix><cid-version><multicodec-content-type><multihash-content-address>
```

## References

- This meeting https://github.com/ipfs/developer-meetings/blob/master/sessions/deep-dive/base32.md
- Very first CID document https://github.com/ipfs/specs/issues/130
- go-ipfs: Make base32 CIDv1 the default for go-ipfs https://github.com/ipfs/go-ipfs/issues/4143
- Use multihashes, not CIDs, when checking if a CID is in a wantlist. https://github.com/ipfs/go-ipfs/issues/4189
- Discussion Point: Using Multihash not CID in blockstore and bitswap https://github.com/ipfs/go-ipfs/pull/4284
- go-cid: Provide Way of Representing CidV0 objects in an alternative base https://github.com/ipfs/go-cid/issues/34
- Forbid non-cryptographic hashes within /ipfs namespace https://github.com/ipfs/go-ipfs/issues/4371

## CIDv0 vs CIDv1

```
<cidv0> ::= <multihash-content-address>
<cidv1> ::= <multibase-prefix><cid-version><multicodec-content-type><multihash-content-address>
```

## Solution Milestones

1. All tools and libraries recognize and are able to produce CIDv1 in Base32 and are able to convert CIDv0 to CIDv1
2. (Open for debate) Lookup for CIDv1 returns peers that has the same multihash from CIDv0 era
3. Everything uses CIDv1 by default


## Problem #1: how to convert CIDv0 to CIDv1?

We need a way to represent CIDv0 in case-insensitive way for safe use in UIs and URLs.

### Potential Solution (1A)

Create CIDv1 with `<multihash-content-address>` from CIDv0
 * breaks old clients/objects: why?

### Potential Solution (1B)

Converting CIDv0 to CIDv1 with a twist: Create CIDv1 but set `<cid-version>` to `0` (producing the `baby` prefix)
 * breaks old clients/objects too: why?
 * requires change to binary format of CID (may be a  NO, NO)
 * horrible hack

### Potential Solution (1C): CIDv0 with multibase

Encode binary CIDv0 binary representation with multibase
  * Not defined in https://github.com/ipld/cid#decoding-algorithm
  * Should work in go
  * Doens't change binary representation

## Problem #2: how to make lookups work with CIDv1 that was created from CIDv0?

### Potential Solution (2A)

Change the blockstore to use multihash instead of CID. Migration needed. Can retrieve data from v0 or v1 CID.

* Possible issues with garbage collection
* Possible changes to refs.local
* Quite a lot of effort required

### Potential Solution (2B)

Use hacky CIDv1 representation suggested in 1B:

> Create CIDv1 but set `<cid-version>` to `0` (producing the `baby` prefix)

Will lookup work?

### Potential Solution (2C)

Convert CIDv0 to CIDv1 on the fly on first read and update datastore?

## Create tests for edge case scenarios

Does solution pass this requirement?

### Make CIDv1 lookup work and retrieve data added in CIDv0 era:
  1. ipfs.add → get CIDv0
  2. convert CIDv0 to CIDv1
  3. request CIDv1 from public gateway, it returns data added in step 1 
     (without dupplicating data or doing two lookups/fs reads)
 
Or is it too difficult and we need to live with the "data duplication/lookup split"?

## Other notes / problems to consider

### Blockstore?

- the ominous "Lisbon treaty" declared that everything should operate on multihashes or ideally opaque binary identifiers
    - but then both go-ipfs and js-ipfs went with binary-form CIDs as keys instead
    - that means the same data will be stored separately, depending on whether CIDv0 or CIDv1 is used
    - that means the same data, if stored with CIDv0 key, will not be cat'able or fetchable with a CIDv1 key
- Iteration over Blockstore
    - ipfs refs local command
    - switching the blockstore keys to multihash as originally planned, would prevent us from iterating over the blockstore and printing CIDs
- GC
    - is okay, since its iterating originates from the pin roots, not from a list of keys in the blockstore
        - the pin roots contain CIDs, so we can still mark everything that should stay, and remove all the rest

### Bitswap?

- bitswap operates on binary-form CIDs
    - same multihash/CID issues as Blockstore
- related: changing hashes, see below

## Changing hashes on ipfs add, ipfs dag put

- The big drawback of changing default options for the data structures built by these commands
  is that hashes will change. A helpful thing to do would be:
  - have flags for *all* relevant options (cid version, multicodec, chunking, etc.)
  - output the flags used, in a way that users can paste them right into the next command
  - make recommendation to users: if you rely on consistent hashes, be explicit about these options




## Solution Matrix

Let's compare different solutions  using various criteria and pick best solution.

Help needed: what are other criteria to consider?


| Criteria                      | Solution 2A "switch blockstore key to multishash" | Solution 2B "CIDv1 with version set to 0" |
| --------                      | -------- | -------- |
| Conform to current spec for CID     |  ✔️ Yes     | ?     |
| Lookup for CIDv0 represented as CIDv1 work   |  ?     |   ?   |
| Lookup works without data duplication in datastore | ? | ? |
| Lookup works without hitting datastore twice | ? | ? |
| Easy to implement | ❌ | ✔️ |
| Does not require datastore migration |  ❌ | ✔️ |
| No confusion for CID consumer | ✔️ | ❌ |
