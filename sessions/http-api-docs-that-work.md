# Building HTTP API Docs that Work

The HTTP API is arguably our most important API — the primary recommended use of IPFS is for people to run a daemon in one process and control it via the HTTP API in another — so it needs to be well documented. Let’s figure out how to fix that.

**Activity/Agenda:**
1. Introduce some of the primary issues that users run into
2. Depending on group size, work together or break into small groups to write our ideal documentation for a selected set of endpoints (e.g. a straighforward one like `/cat`, a complicated one like `/get` or recursive adds in `/add`, a weird one like `/p2p/listener/open`, and one that isn't implemented everywhere like `/mount`)
3. Reconcile what’s in our ideal doc with the tools we have today and discuss how to improve our **tools** (expanding `go-ipfs-cmdkit` to fit more info, switching to OpenAPI, just writing docs in Markdown) and **processes** (how do we keep teams in sync/working together [unlike `interface-ipfs-core`] and keep the docs up to date).

**Goal(s):**
- A shared understanding of the ways in which the HTTP API docs fall down
- An idea of what we want/need them to look like
- A plan (or at least a set of tools) for getting to that ideal

**Duration:** Ideally 60 (so we can work through more than one endpoint *and* discuss approaches), but it might be possible to trim this down to 30.

**Participation:** At least a couple people who come from more from the user side and at least one primary contributor from each of `go-ipfs` and `js-ipfs`.
