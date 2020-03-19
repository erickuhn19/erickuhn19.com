---
layout: post
title: Bitcoin P2P e-cash paper
time: 2008-11-10 02:14:30
categories: emails
list: Cryptography Mailing List
---
[Source](http://www.metzdowd.com/pipermail/cryptography/2008-November/014842.html) - [Nakamoto Institute](https://satoshi.nakamotoinstitute.org/emails/cryptography/9/#selection-15.0-15.19)

[Email Index](/satoshi/emails) - [Back](/emails/2008/11/09/cryptography-8) - [Next](/emails/)

*>James A. Donald wrote:*

*> Furthermore, it cannot be made to work, as in the proposed system the work of tracking who owns what coins is paid for by seigniorage, which requires inflation.*

___

If you're having trouble with the inflation issue, it's easy to tweak it for transaction fees instead. It's as simple as this: let the output value from any transaction be 1 cent less than the input value. Either the client software automatically writes transactions for 1 cent more than the intended payment value, or it could come out of the payee's side. The incentive value when a node finds a proof-of-work for a block could be the total of the fees in the block.

Satoshi Nakamoto


---------------------------------------------------------------------
The Cryptography Mailing List
Unsubscribe by sending "unsubscribe cryptography" to majordomo at metzdowd.com
