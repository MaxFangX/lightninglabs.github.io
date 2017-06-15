---
layout: post
title:  "An Overview of the Lightning Network Ecosystem"
date:   2017-06-15 08:00:00 -0800
categories: software lnd lightning
---

![Two Chainzz](https://ae01.alicdn.com/kf/HTB12oWUMVXXXXbSapXXq6xXFXXXy/-font-b-Silver-b-font-Gold-Plated-Stainless-Steel-Necklace-Femme-Boys-Mens-font-b.jpg)


_By Max Fang_

An Overview of the Lightning Network Ecosystem
==============================================

_By Max Fang_

`lnd` is still in alpha, but we're already seeing a handful of developers building on top of it. In this post you can find a summary of the progress made thus far, starting first with application-level projects (**"Lapps"**), a few user interfaces, and concluding with repositories and utilities that developers on Lightning will find helpful.

---

# Lapps

### Slack Tipbot ([link](https://github.com/CryptoFR/ln-tip-slack))

*by François Masurel* ([@francoismasurel](https://twitter.com/francoismasurel))

![users tip Max on Slack](http://imgur.com/CNnMvfM.jpg)

What's the first thing a Bitcoiner builds with micropayments? A tip bot! The `lnd`-based successor to ChangeTip, Francois Mably and team built a tip bot on Slack, which is still WIP but usable on Bitcoin testnet. After depositing funds, you simply have to type /lntip <amount in satoshis> @<Slack username> to send a tip. You can try it out here: [https://lnd-testnet-2.mably.com/](https://lnd-testnet-2.mably.com/)

![image alt text](http://imgur.com/eHLym7J.jpg)

---

### Voltachain

*by Louis Congard ([@Aldhyr](https://twitter.com/Aldhyr)), Ali El Husseini, Tangui Clairet, Pierre Lorcery ([@tulsene](https://twitter.com/tulsene)), François Masurel ([@francoismasurel](https://twitter.com/francoismasurel))*

![image alt text](https://i.imgur.com/1lZoZDe.png)

[TODO Replace picture with Embed tweet [https://twitter.com/Aldhyr/status/841055635286458370](https://twitter.com/Aldhyr/status/841055635286458370)]

Voltachain is a pay-as-you-go solution for electric vehicle energy purchases, using `lnd` as its basis for micropayments. Rethinking the current model of flat-rate pricing, Voltachain allows people to pay for only the power that they actually consume. Furthermore, since Voltachain is peer-to-peer and users are not locked into centralized vendors, anyone can easily spin up a pay-as-you-go charging service of their own.

The team demoed their PoC live at the Merkleweek hackathon in Paris using a smartphone connected to a charging station that initially produced no charge. Clicking a button on a web interface completed a payment from the phone to the charging station, and the phone lit up at once and promptly began charging.

`lnd` could also be used for video streaming, internet by the megabyte, and paid API calls. Props to Voltachain for being the first to apply Bitcoin micropayments to energy and taking home first place at Merkleweek!

![image alt text](https://i.imgur.com/nuDTQun.png)

*Sequence diagram of the Voltachain PoC*

---

### "Monetizing Full Nodes"

*by **Michael Folkson (@michaelfolkson), Alex Bosworth (@alexbosworth), and Nathan Basanese** (@NathanBasanese)*

[https://github.com/michaelfolkson/bcoin-hackathon](https://github.com/michaelfolkson/bcoin-hackathon)

As the Bitcoin blockchain grows bigger in size, it gets more and more cost-prohibitive for individuals in the network to run full nodes, potentially leading to centralization. To directly address this problem, Michael Folkson, Alex Bosworth, and Nathan Basanese built "Monetizing Full Nodes," a solution allowing full nodes to generate revenue and potentially even profits. Monetizing Full Nodes utilizes `lnd` for payments, bcoin for full nodes, and RiskBazaar as a "risk contract". In particular, full nodes could generate revenue by serving as oracles for other nodes seeking information about the state of the Bitcoin network. A RiskBazaar contract would facilitate the information exchange, while the Lightning Network would facilitate the payment of the associated fees to the full node. Their application took home first place at the bcoin hackathon this March in SF!

You can read their explanation of the project [here](https://medium.com/purse-essays/bcoin-hackathon-bitcoin-for-your-thoughts-3b7e7c067970) and find their demo slides  [here](https://www.slideshare.net/michaelfolkson/bcoin-hackathon-slides).

---

# User Interfaces

### Lightning MacOS GUI Wallet

*by Alex Bosworth (@alexbosworth)*

[https://github.com/alexbosworth/lnd-gui](https://github.com/alexbosworth/lnd-gui)

Alex Bosworth built the first `lnd` User Interface for Mac OS! You can see a preview of it here:

TODO Embed tweet [https://twitter.com/alexbosworth/status/844030573131706368](https://twitter.com/alexbosworth/status/844030573131706368)

---

### Lightweight LND Dashboard

*by François Masurel (@francoismably)*

[https://github.com/mably/lncli-web](https://github.com/mably/lncli-web)

Francois Mably and team also built a web client and dashboard for `lnd` written in NodeJS / Angular. A few of the other `lnd` projects have used this web client as a starting point, speaking to the usefulness of this project. Here are a few screenshots:

![image alt text](https://i.imgur.com/d6lh9YN.png)

![image alt text](https://i.imgur.com/7jhnPmU.png)

You can find more screenshots here [[https://imgur.com/a/LgWcs](https://imgur.com/a/LgWcs)]

---

### Mobile and Desktop app for Lightning

*by Jack Mallers (@JackMallers)*

We are excited to hear that there's developer energy toward building a mobile and desktop application for the Lightning Network. This in-progress app plans to support both bitcoin and litecoin, featuring a slick UI. Watch Alex 'buy a coffee' for certain special guest of his here:

TODO embed tweet [https://twitter.com/JackMallers/status/857357930777149440](https://twitter.com/JackMallers/status/857357930777149440)

---

# Developer Infrastructure

Lightning recently hired me to work on developer tooling and resources - stay tuned for the full site! If you want to try building on `lnd` now, there are a few tools and guides at your disposal:

---

### Getting Started

[https://github.com/lightningnetwork/lnd/blob/master/README.md](https://github.com/lightningnetwork/lnd/blob/master/README.md)

To get started, follow this root README.md of the `lnd` repository as well as the associated installation guides.

---

### Guide: Creating a Lightning Cluster

[https://github.com/lightningnetwork/lnd/blob/master/docker/README.md](https://github.com/lightningnetwork/lnd/blob/master/docker/README.md)

This guide details how to run a local dockerized cluster of `lnd` nodes, connecting the major components together, opening/closing channels, and connecting to the Lightning faucet node. Accessing the standard manual via `lnd --help` at the command line is also helpful.

---

### Guide: `lnd` gRPC server

[https://github.com/lightningnetwork/lnd/blob/master/docs/grpc/javascript.md](https://github.com/lightningnetwork/lnd/blob/master/docs/grpc/javascript.md)

[https://github.com/lightningnetwork/lnd/blob/master/docs/grpc/python.md](https://github.com/lightningnetwork/lnd/blob/master/docs/grpc/python.md)

The primary way to connect applications to `lnd` is through the gRPC server. We have written guides on how to write a simple gRPC client for both Javascript and Python. If you're not familiar with the concept of RPC, you can also read more about gRPC itself at [http://www.grpc.io/](http://www.grpc.io/)

---

### `lnd` REST API

[https://github.com/lightningnetwork/lnd/blob/master/lnrpc/rpc.swagger.json](https://github.com/lightningnetwork/lnd/blob/master/lnrpc/rpc.swagger.json)

Lightning features a gRPC proxy that allows you to query a LND node with familiar HTTP requests, which can make development a lot easier for you, since you don't have to connect to a gRPC server. Here are some example `curl` requests by @roasbeef: [https://gist.github.com/Roasbeef/624c02cd5a90a44ab06ea90e30a6f5f0](https://gist.github.com/Roasbeef/624c02cd5a90a44ab06ea90e30a6f5f0)

---

### Lightning Faucet

[https://faucet.lightning.community/](https://faucet.lightning.community/)

![image alt text](https://i.imgur.com/4qtSudA.png)

A faucet for Lightning Network is currently deployed on the Bitcoin testnet. Instead of sending Bitcoin directly on-chain to the targeted user, the faucet will open a channel with the user. Read the code and more information here: [https://github.com/lightninglabs/lightning-faucet](https://github.com/lightninglabs/lightning-faucet)

---

### Code Contribution Guidelines

[https://github.com/lightningnetwork/lnd/blob/master/docs/code_contribution_guidelines.md](https://github.com/lightningnetwork/lnd/blob/master/docs/code_contribution_guidelines.md)

And lastly, for those who may be interested in building `lnd` itself, the code contribution guidelines will outline the skills and readings required, development practiced, and code approval process.
