# Session: Service Worker Gateway/Lib

- **Proposed by:** @lidel
- **Led by:** @hugomrdias @lidel
- **Duration:** 60 minutes
- **Who Should Attend:** @vasco-santos @hugomrdias @lidel 
- **Who has to be there in order for it to work:**  @vasco-santos @hugomrdias @lidel

## Overview

- **Objective:** Bootstrap work on Service Worker Lib for Web Browser apps
- **Activity:** Deep Dive into challenges and ways to solve them
- **Outcome:**  Create work outline, identify open problems

# Proposal

## Authors

- @fsdiogo
- @hugomrdias
- @travisperson
- @vasco-santos

## What?

Create a drop-in JS library that enables developers to integrate the `js-ipfs` node into their app.

## Problems

* Multiple IPFS nodes may be running at the same time in the same browser
* Devs can only register one service worker per origin/scope.

## Motivation

Running an IPFS node is an expensive task. Accordingly, when web applications intend to use them in their context, a solution consists on running the node in a service worker, in order to decrease the resources being consumed in the main thread. However, multiple apps would be running their own node. 

A single browser must be running a single IPFS node. This way, web apps should be able to use a node running in a global domain (eg. `js.ipfs.io`). In addition, this node should be accessible by the applications through post-msg. 

As several applications will be interested in the same features such as a gateway resolver, a set of middlewares should be available. Moreover, apps must be able to have their specific logic for hijacking the HTTP requests.

## Solution proposal

**Global Service Worker**

```
  ______________________________
 |                              |
 |  js.ipfs.io Service Worker   |
 |                              |
 |     ____________             |
 |    |            |            |
 |    | IPFS NODE  |            |
 |    |____________|            |
 |                              |
 |______________________________|

Domain: js.ipfs.io
Version: js.ipfs.io/v0 (the sw must be versioned)
Task: Run a simple IPFS node
```

**Usage**

1. Main thread usage

```
  ________________________________________
 |                                        |
 |  Main thread                           |
 |                                        |
 |     ________                           |
 |    |        |                          |
 |    | iframe | => API postmsg-proxy     |
 |    |________|                          |
 |                                        |
 |________________________________________|


const createIframe = require('ipfs-service-worker');

const ipfs = createIframe();

// ipfs is an instance of the ipfs-postmsg-proxy
// https://github.com/tableflip/ipfs-postmsg-proxy
```

2. Service Worker usage (IPFS Node in another SW)

```
  ________________________________________
 |                                        |
 |  example-domain.com                    |
 |                                        |
 |     ________                           |
 |    |        |                          |
 |    | iframe | => API                   |
 |    |________|                          |
 |                                        |
 |________________________________________|


const { gatewayResolver } = require('ipfs-sw-gateway-midleware');

const specificDomainLogic =(ev) => {
  // domain specific logic
};

self.addEventListener(gatewayResolver(specificDomainLogic));

// The event listener can receive a chain of middlewares;
// the idea is to have a bunch of them with multiple functionality
// i.e gatewayResolver, downloadStream, etc.
```

3. Download from Gateway

Anchor elements have a `download` property that works on same origins to allow links to force a download prompt (query argument). When tested this also works with service workers.

## Possible Problems

We need to rely on `ipfs-postmsg` and guarantee feature parity.

## References

- https://github.com/ipfs-shipyard/service-worker-gateway
- https://github.com/ipfs/ipfs-service-worker
- https://github.com/tableflip/window.ipfs-fallback
- https://github.com/tableflip/ipfs-postmsg-proxy
