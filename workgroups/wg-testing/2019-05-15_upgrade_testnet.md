2019-05-15 Upgrade Testnet
==========================

On May 15, 2019 the Bitcoin Cash network will undergo a planned protocol upgrade, as part of a series of regularly scheduled network upgrades. The changes have been [specified](https://github.com/bitcoincashorg/bitcoincash.org/blob/master/spec/2019-05-15-upgrade.md) and implemented three months prior to upgrade activation in order to permit the ecosystem to prepare well in advance.

To assist technical preparations for the upgrade, a testnet is available where the upgrade features can be trialed and tested. Node implementations, wallets, businesses and services built on the Bitcoin Cash network can use this testnet to ensure compatibility, or to get started building products to make use of the upgrade features. This document outlines the information needed to participate in this upgrade testnet.

To communicate and coordinate with other Upgrade Testnet participants, please join the Telgram group at: https://t.me/joinchat/DUeWWkYZbVMjvwMTRFlRhw

## Upgrade Testnet Parameters

New Activation: 1557630000

Upgrade Testnet users please be advised: we will be doing a new upgrade activation at the MTP timestamp 1557630000. This corresponds to Sunday, 12 May 2019, at 03:00:00 UTC, or Saturday, 11 May at 20:00 Pacific time.

The plan of events will be as follows:

* May 9th ~12:00 UTC (Thursday morning PST) - mining will cease on the Upgrade Testnet. Miners and nodes can re-sync to the regular testnet.
* May 9th ~ 23:00 UTC (Thursday afternoon PST) afternoon. Miners will invalidate a block to split from main testnet. Shortly after this happens, the block hash will be shared in this channel so all Upgrade Testnet participants can also invalidate the same block.
* May 12 03:00 UTC (20:00 Saturday evening PST), Upgrade will activate when MTP reaches this timestamp.

All participants should re-join the regular testnet, and set a new activation time by doing the following commands:

```
rm ~/.bitcoin/testnet3/banlist.dat

bitcoind -testnet -greatwallactivationtime=1557630000 -addnode=testnet.imaginary.cash

bitcoin-cli -testnet reconsiderblock 0000000000000294acbf8b48cdb725053f4f375252be85717165f1fac4155a28
```

[Wait for node to sync to regular testnet chain tip]

```
bitcoin-cli -testnet invalidateblock 00000000000000c811de2e5b1935a533197dbe0abeec0eb91ee9f7013aa2da06
```

After invalidating the block, you should check that you are synced to the correct chain tip by checking with the Upgrade Testnet explorer listed below.

The last common block is `0000000000000040e2b67e0e5cf5c2477245b221549ad1531b24cac9eef8db4f` (height 1302953).

Further information will be posted as it becomes available.

## Other services

Miners: to `testnet.imaginary.cash:19338`
user: (testnet address) password:(anything)

Electrumx server: `testnet.imaginary.cash:50002` will follow the bitcoind.

Electron Cash Schnorr edition: https://github.com/markblundeberg/Electron-Cash/tree/schnorr
(only produces schnorr sigs)

Insight API: http://testnet.imaginary.cash/api/BCH/testnet/ 

Explorers: 
 - http://testnet.imaginary.cash
 - http://190.123.23.9:3001/insight/
 
Transaction broadcaster: http://190.123.23.9:3001/insight/tx/send

Faucet: http://190.123.23.9:3002/

## Communication

To communicate and coordinate with other Upgrade Testnet users, you can join the [Testing Workgroup](workgroup.md) and its associated [Telegram Group](https://t.me/joinchat/DUeWWkYZbVMjvwMTRFlRhw).
