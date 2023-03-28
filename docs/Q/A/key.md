---
layout: default
title: What is the key innovation?
parent: Q&A
nav_order: 4
---

# What is the key innovation?

Building our own infrastructure to support index fund products was a big challenge, but it comes with a lot of perks. We have complete customizability from the top down, which makes it really easy to upgrade contracts for new user capabilities, product features, and plugging in other protocols like staking.

Deep inside the infrastructure, we took a unique approach to designing the investment pools. For each pool that's initialized, a resource account is created in the code, and funds are stored on that account. A ledger is created to keep track of investments into the pool, which are essentially token transfers to that non-human account. The only functions to interact with a pool are the highly protected invest() and withdraw().

Withdrawing relies on the balance stored in the ledger, which can only be updated by investing from a governed list of tokens. Naturally, the resource accounts and ledgers are not accessible. In other words, the token transfer processes are foolproof. This insulates any fund from being drained by a single account. What we expect to see is funds where some investments are never withdrawn, because users lose their keys - part of the trade-off of building complete self-custody for investors.

Our protocol innovations allow us to design index funds where the manager can collect a fee, automate rebalancing, update their fund allocation, and set minimum withdrawal/contribution requirements without an ability to access any of the funds that are invested.