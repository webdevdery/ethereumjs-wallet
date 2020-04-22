# ethereumjs-wallet

## Index

### Classes

- [EthereumHDKey](classes/ethereumhdkey.md)
- [Wallet](classes/wallet.md)
- [WalletSubprovider](classes/walletsubprovider.md)

### Interfaces

- [EtherWalletOptions](interfaces/etherwalletoptions.md)
- [EvpKdfOpts](interfaces/evpkdfopts.md)

### Functions

- [fromEtherCamp](#fromethercamp)
- [fromEtherWallet](#frometherwallet)
- [fromKryptoKit](#fromkryptokit)
- [fromQuorumWallet](#fromquorumwallet)

---

## Functions

<a id="fromethercamp"></a>

### fromEtherCamp

▸ **fromEtherCamp**(passphrase: _`string`_): [Wallet](classes/wallet.md)

_Defined in [thirdparty.ts:169](https://github.com/ethereumjs/ethereumjs-wallet/blob/15de3c4/src/thirdparty.ts#L169)_

Third Party API: Import a brain wallet used by Ether.Camp

**Parameters:**

| Name       | Type     |
| ---------- | -------- |
| passphrase | `string` |

**Returns:** [Wallet](classes/wallet.md)

---

<a id="frometherwallet"></a>

### fromEtherWallet

▸ **fromEtherWallet**(input: _`string` \| [EtherWalletOptions](interfaces/etherwalletoptions.md)_, password: _`string`_): [Wallet](classes/wallet.md)

_Defined in [thirdparty.ts:121](https://github.com/ethereumjs/ethereumjs-wallet/blob/15de3c4/src/thirdparty.ts#L121)_

**Parameters:**

| Name     | Type                                                               |
| -------- | ------------------------------------------------------------------ |
| input    | `string` \| [EtherWalletOptions](interfaces/etherwalletoptions.md) |
| password | `string`                                                           |

**Returns:** [Wallet](classes/wallet.md)

---

<a id="fromkryptokit"></a>

### fromKryptoKit

▸ **fromKryptoKit**(entropy: _`string`_, password: _`string`_): [Wallet](classes/wallet.md)

_Defined in [thirdparty.ts:176](https://github.com/ethereumjs/ethereumjs-wallet/blob/15de3c4/src/thirdparty.ts#L176)_

Third Party API: Import a wallet from a KryptoKit seed

**Parameters:**

| Name     | Type     |
| -------- | -------- |
| entropy  | `string` |
| password | `string` |

**Returns:** [Wallet](classes/wallet.md)

---

<a id="fromquorumwallet"></a>

### fromQuorumWallet

▸ **fromQuorumWallet**(passphrase: _`string`_, userid: _`string`_): [Wallet](classes/wallet.md)

_Defined in [thirdparty.ts:265](https://github.com/ethereumjs/ethereumjs-wallet/blob/15de3c4/src/thirdparty.ts#L265)_

Third Party API: Import a brain wallet used by Quorum Wallet

**Parameters:**

| Name       | Type     |
| ---------- | -------- |
| passphrase | `string` |
| userid     | `string` |

**Returns:** [Wallet](classes/wallet.md)

---
