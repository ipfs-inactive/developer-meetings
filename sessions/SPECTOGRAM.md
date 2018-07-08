# Activity (Partial Session): Placing People in the Landscape 

_This is a spectrogram exercise that we will do as the second half of our opening session on Day 1._

**Proposed by** @flyingzumwalt  
**Led by** @flyingzumwalt & @diasdavid  
**Duration** 30-45 minutes  
**Who Shoud Attend:** Everyone  
**Who has to be there in order for it to work:** Everyone who owns KRs, especially WG captains, Tech Leads and Product Managers

## Overview

- **Objective**: At the beginning of the developer meetings, give everyone a sense of where people fit into the landscape of teams, products and Working Groups
- **Activity**: Do a Spectrogram exercise (see details below). Take a photo each time you populate a new spectrum.
- **Outputs**: Everyone has seen who works on, or relies on, the various teams and WGs, and we have photos of those groups!

## Details

In this exercise, we use our bodies to create spectrograms that represent where we lie on some spectrum. It's usually done with everyone lined up along a wall. The organizer defines the ends of the spectrum -- ie. "I like dogs and hate cats" at one end of the room and "I like cats and hate dogs" at the other end of the room. The participants then place themselves along the spectrum based on their inclinations about cats and dogs. 

### Our Spectrogram layout:

For this exercise we will use a fixed layout, where the people who are on the team of maintainers for a given library, Working Group, etc stand at one end of the room, people who _use_ or _directly rely on_ their work stand at the other end. The middle ground represents people who contribute without being a full-time maintainer on the associated team.

    |-------------------|-------------------|

    I use it       I contribute      I work on it full time

Have people place themselves on this spectrum for a variety of teams, products and Working Groups. 
- If you are neither a user, contributor, nor team member, step off the spectrum.
- If you contribute a lot, stand closer to the maintainers. If you contribute a little, stand closer to the "I use it" end of the room.
- "I use it" should mean that you directly interact with the libraries, APIs, or activities concerned (ie. if you use IPFS but never directly use IPLD, don't stand in the "I use IPLD" group even though you benefit indirectly from IPFS using IPLD.) Let the spectrum reflect the people who are directly engaged in using or maintaining that technology.

### Spectra to Plot

The core protocols & implementations
- Any IPFS implementation
- js-ipfs
- go-ipfs 
- Any libp2p implementation
- js-libp2p
- go-libp2p 
- rust-libp2p
- Any IPLD implementation
- js-ipld 
- go-ipld 

Working Groups
- GUI WG
- Web Browsers WG
- Infra Team 
- Dynamic Data Structures and Capabilities WG

Categories of Use
- IPFS for Distributed Apps
- IPFS for Off-Chain (Blockchain) Data
- IPFS for Audio or Video Media
- IPFS for Data Stewardship
- IPFS for Data Analysis and/or Machine Learning
- IPFS on Mobile

Products
- peer*
- peerpad 
- orbit-db
- ??? 


## Some considerations

- **This should be done early in the meetings**, ideally at the beginning of day one, so everyone has a shared basic understanding of who does what, and who they might want to talk to during the week.
- **More permutations, less chatter.** Let's try to make this run smoothly and efficiently, allowing people to get a rapid-fire sense of the landscape. Make sure all the WG members understand the exercise in advance, to minimize confusion. Don't invite a bunch of chatter, commentary and crosstalk when each spectrogram forms. Just form the spectrogram, let the no-photo people step out, snap the photo, and move on.
- **We need a stand-in for @pgte**, who can't attend the meetings but is TL and captain of a bunch of important stuff. Maybe have one of the Protocol Labs helpers like @miyazono wear a @pgte mask.
- **If people don't want to be photographed**, could we let them step out of the photo while people hold a sign with their github handle?

