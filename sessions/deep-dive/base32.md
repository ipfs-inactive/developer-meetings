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

