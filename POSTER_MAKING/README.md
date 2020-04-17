# Poster-Making and Poster Viewing

## Videos

# [Poster Sessions Playlist](https://www.youtube.com/playlist?list=PLuhRWgmPaHtQrb8rpywj8r0dwYvUzJhoJ)
- [Poster Session - DHT](https://youtu.be/JfjpwKzulhE)
- [Poster Session - Functional encryption](https://youtu.be/D-_2JhlxN9k)
- [Poster Session - IPNS](https://youtu.be/Ga-RyAbtPHQ)
- [Poster Session - IPRS](https://youtu.be/md7O4eHNfzY)
- [Poster Session - Peer Routing](https://youtu.be/no5WldtLJCk)
- [Poster Session - Rendezvous](https://youtu.be/4XPS_50KU54)
- [Poster Session - Secio](https://youtu.be/WYmhEA2dABI)
- [Poster Report - Bitswap](https://youtu.be/xTBm1skAfiY)
- [Poster Report - DHT](https://youtu.be/yLFsTpyZC8c)
- [Poster Report - DWEB Addressing](https://youtu.be/CtIvqMf0Gi8)
- [Poster Report - Floodsub](https://youtu.be/i0gFQO4kSfc)
- [Poster Report - IPLD](https://youtu.be/2H5dP1hAqZM)
- [Poster Report - IPNS](https://youtu.be/PYlRzbtVCZ0)
- [Poster Report - Mutable File System](https://youtu.be/TwYAGDGKDOw)
- [Poster Report - Multi Key](https://youtu.be/NEHb8SiQMIE)
- [Poster Report - Peer Pad](https://youtu.be/QsE28NhEloU)
- [Poster Report - UNIXFX](https://youtu.be/Cvv_8cpoB6k)

## Overview

- **Objective**: Get people to learn some part of the code base in depth and through that process of learning, create materials that can be used by others to learn that part of the code base. Promote collaboration, knowledge transfer through deep dives and generation of materials that can be used by others in the future.
- **Activity**: These sessions consist on gathering people into small groups (2~4) to explore and understand in depth one of the selected topics. At the end of the session, everyone should have a poster ready (this will be fun!). At the end of each day, all of the poster groups will give a one-minute presentation of their poster.
- **Outcome**: The posters and discussions will then be converted into docs and/or specs to the IPFS repos.

## Format

Have fun working in small groups to create posters and other documentation, then give a one-minute presentation of your work. [Original proposal and discussion of the format ipfs/conf#43](https://github.com/ipfs/conf/issues/43).

Purpose: Get people to learn some part of the code base in depth and through that process of learning, create materials that can be used by others to learn that part of the code base.

**Duration** 75 minutes

**Who Should Attend:** Anyone who wants to learn or share knowledge by making a poster in a small team

**Who has to be there in order for it to work:** Anyone who wants to either share knowledge or do a bit of research and put findings in a poster.

## Details

During this session, use your time to learn some part of the code base in depth together with a small team of collaborators. Together, create a poster that others can use to learn about that part of the code base.

Some of the things to do during this session together with the other people on your poster team:

- **Review any formal documentation** relevant to the topic you've chosen
- **Find and read all the "pseudo-specs"** -- gather and read through all the partial documentation that's floating around. Discuss it together.
- **Look through the related code**
- **Look for relevant reference materials**: papers, recordings of talks, etc.
- **Clarify and test your understanding** by discussing all of this information
- **Interact with experts in the room** - people like Tech Leads will be circulating around the groups
- **Compile all of this information** into something that's easy to consume (a poster)
- **Plan how this information can be incorporated** into the existing documentation and repositories.
- **Choose who will present your poster.**
- _If you have time, submit a PR with your new info into the corresponding repository._

At the end of the day, each group will have 1 minute to present their poster. Make sure to choose in advance who will be presenting.

## How you will choose which poster to work on

Poster teams should have a maximum of 4 people and a minimum of 2. People will choose which poster to work on using this process:
- Leading up to the session, anyone can propose poster topics using the [instructions below](#proposed-poster-making-sessions)
- The meeting organizers will draw a spot on the ground for each of the posters.
- Before the start of the session, everyone must stand on the poster topic they want to work on. If more than five people try to join a topic, you must re-balance people to other topics.
- When everyone has chosen a topic and no topics have more than five people, write down the list of participants for that topic.
- Take a flip chart, markers, etc and work wherever you want to work.

# Proposed Poster Topics

If you want to propose a poster topic, add it here (via a Pull Request). Optionally use the [template](../_template.md) to provide a fuller description of the session and link to it from your entry in the table below.

_We're aiming to have at least 15 poster topics for people to choose from._

| Topic | Proposed by | Description |
|---|---|---|
| 🌟 unixfs | @diasdavid | What is Unixfs, how does it work, what are its data structures and what are the shortcomings that lead into the research of UnixfsV2?
| 🌟 How does Bitswap work? | @diasdavid | The Decision Engine and the ledger; how reproviding happens; what is Bitswap 1.0.0 vs Bitswap 1.1.0? Is there a tit-for-tat? |
| 🌟 How does IPLD enable IPFS to traverse through multiple types of hash linked-data | @diasdavid |
| 🌟 MFS - Mutable File System && Files API | @diasdavid |
| 🌟 PeerPad Capabilities System | @diasdavid |
| 🌟 Pinning and Garbage Collection on IPFS | @diasdavid |
| libp2p connection flow | @diasdavid | What is the connection flow of a libp2p connection? What happens internally and why? (what is the libp2p-switch) |
| 🌟 Explain the IPFS DHT | @diasdavid | How does the DHT of IPFS work? Make the distinction between Peer Routing and Content Routing
| 🌟 IPNS - InterPlanetary Naming System | @diasdavid | TBD
| 🌟 The intrinsicacies of DWeb Addressing | @diasdavid | The challenges with the origin policy and all details to have in consideration when adding IPFS natively to Web Browsers resolution.
| 🌟 KeyStore & Linked Data Key (aka Multikey) | @diasdavid |
| 🌟 The design of the IPFS Repo | @diasdavid |
| 🌟 DEX - The Importers and Exporters Project | @diasdavid |
| 🌟 FloodSub | @diasdavid | Implementation, Design & Shortcommings, what is next
| 🌟 gx | @diasdavid | What is gx, how does it work, benefits, pros, cons
| 🌟 InterPlanetary Test Lab | @diasdavid |
| CAR | @diasdavid | Content Addressed Archives
| PDD | @diasdavid | Protocol Driven Development
| SECIO | @diasdavid | How does SECIO work?
| Rendezvous Protocol | @diasdavid | What is the Rendezvous protocol? How do IPFS and libp2p use it?
| IPRS - InterPlanetary Record System | @diasdavid |
| The collection of Multiformats | @diasdavid |
| Protocol and Stream Multiplexing | @diasdavid |
| Circuit Relay | @diasdavid |
| dnslink | @diasdavid |
| xTP - External Transports | @diasdavid |
