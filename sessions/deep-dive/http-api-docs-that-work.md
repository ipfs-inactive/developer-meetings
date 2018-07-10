# Designing HTTP API Docs that Work

- Proposed by: @Mr0grog
- Led by: @Mr0grog
- Who Should Attend: At least a couple people who come from more from the user side and at least one primary contributor from each of `go-ipfs` and `js-ipfs`

The HTTP API is arguably our most important API — the primary recommended use of IPFS is for people to run a daemon in one process and control it via the HTTP API in another — so it needs to be well documented and well tested. Let’s work together to design what improved docs should look like, how we can make the docs and the API testable, and find some people willing to take responsibility for it.

Note there is another deep dive on redesigning the API iteself (“Upgrading the HTTP-API to a RPC API”). We’ll still need to maintain the HTTP API for a while and, even after switching over, much of what we discuss here about designing the docs and tests should still be applicable.

**Activity/Agenda:**
1. Introduce some of the primary issues that users run into
2. Depending on group size, work together or break into small groups to write our ideal documentation for a selected set of endpoints (e.g. a straighforward one like `/cat`, a complicated one like `/get` or recursive adds in `/add`, a weird one like `/p2p/listener/open`, and one that isn't implemented everywhere like `/mount`)
3. Reconcile what’s in our ideal doc with the documentation tools we have today and discuss how to improve our **tools** (expanding `go-ipfs-cmdkit` to fit more info, switching to OpenAPI, just writing docs in Markdown) and **processes** (how do we keep teams in sync/working together [unlike `interface-ipfs-core`], how keep them up to date, and how to use them to validate the go-ipfs and js-ipfs implementations).

**Goal(s):**
- A shared understanding of the ways in which the HTTP API docs fall down
- An idea of what we want/need them to look like
- A plan or set of tools for getting to that ideal
- At least one person responsible for the effort to implement all this :)
