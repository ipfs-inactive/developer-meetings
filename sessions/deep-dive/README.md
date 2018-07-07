# Deep Technical Design

[Original proposal and discussion of the format ipfs/conf#43](https://github.com/ipfs/conf/issues/43).

- **Duration:** 60-90 minutes  
- **Who Should Attend:** People who want to engage in deep technical design work  
- **Who has to be there in order for it to work:** Session leaders who have the necessary design knowledge for the chosen topic

## Overview

- **Objective:** Deep knowledge transfer that only happens in synchronous interactions.
- **Activity:** In a group of max 4 people, dive deep on a complex technical design topic.
- **Outcome:** The output of each of these session would be a RFC like document (can be very raw) that describes the proposed solution (even if with known shortcomings), or it could be a map of all the important concepts, obstacles, and related topics you covered in the session.

## Details

One of the things that we did a lot in the first couple of years of IPFS was to really dive deep and paint the bike shed in order to come up with things such as IPLD, PubSub and other advancements to the original IPFS protocol. These design sessions were intense and they were not about explaining how things work, they were focused on finding the solution with the knowledge and resources we had available.

These deep technical design sessions will attempt to revive that and allow others experience it. We have a bunch of open problems (e.g. Private DHT, scale up the DHT, reduce the information leakage on a libp2p dial, GraphSync, etc).

# Proposed Deep Dive Sessions

If you want to propose a deep dive session, add it here (via a Pull Request). Optionally use the [template](../_template.md) to provide a fuller description of the session.

| Topic                    | Proposed by  | Necessary Participants | Description |
|:------------------------:|:------------:|:----------------------:|:-----------:|
| Private DHT | @diasdavid | ???          | TBD | |
| Scaling up the DHT       | @diasdavid   | ??? | TBD |
| Reducing the information leakage on a libp2p dial | @diasdavid | ??? | TBD |
| GraphSync                | @diasdavid   | @diasdavid, @stebalien, @vmx | [details](graphsync.md) |
| Locking the IPFS repo for concurrent access | @alanshaw | @diasdavid @achingbrain @alanshaw @pgte @hugomrdias @satazor @lidel @olizilla | How do we manage concurrent access to an IPFS repo when we have multiple tabs on the same domain or web workers or service workers? How do we avoid being too restrictive (i.e. locking everything) whilst guarding against race conditions and concurrency problems? |
|Proposing and Discussing Open Research Questions | @miyazono| N/A | Increase awareness of the RFP program and research discussion repo, and source open problem ideas |
