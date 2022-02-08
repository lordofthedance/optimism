[@eth-optimism/sdk](../README.md) / [Exports](../modules.md) / StandardBridgeAdapter

# Class: StandardBridgeAdapter

Bridge adapter for any token bridge that uses the standard token bridge interface.

## Hierarchy

- **`StandardBridgeAdapter`**

  ↳ [`ETHBridgeAdapter`](ETHBridgeAdapter.md)

  ↳ [`DAIBridgeAdapter`](DAIBridgeAdapter.md)

## Implements

- [`IBridgeAdapter`](../interfaces/IBridgeAdapter.md)

## Table of contents

### Constructors

- [constructor](StandardBridgeAdapter.md#constructor)

### Properties

- [estimateGas](StandardBridgeAdapter.md#estimategas)
- [l1Bridge](StandardBridgeAdapter.md#l1bridge)
- [l2Bridge](StandardBridgeAdapter.md#l2bridge)
- [messenger](StandardBridgeAdapter.md#messenger)
- [populateTransaction](StandardBridgeAdapter.md#populatetransaction)

### Methods

- [deposit](StandardBridgeAdapter.md#deposit)
- [getDepositsByAddress](StandardBridgeAdapter.md#getdepositsbyaddress)
- [getTokenBridgeMessagesByAddress](StandardBridgeAdapter.md#gettokenbridgemessagesbyaddress)
- [getWithdrawalsByAddress](StandardBridgeAdapter.md#getwithdrawalsbyaddress)
- [supportsTokenPair](StandardBridgeAdapter.md#supportstokenpair)
- [withdraw](StandardBridgeAdapter.md#withdraw)

## Constructors

### constructor

• **new StandardBridgeAdapter**(`opts`)

Creates a StandardBridgeAdapter instance.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `opts` | `Object` | Options for the adapter. |
| `opts.l1Bridge` | [`AddressLike`](../modules.md#addresslike) | L1 bridge contract. |
| `opts.l2Bridge` | [`AddressLike`](../modules.md#addresslike) | L2 bridge contract. |
| `opts.messenger` | [`ICrossChainMessenger`](../interfaces/ICrossChainMessenger.md) | Provider used to make queries related to cross-chain interactions. |

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:37](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L37)

## Properties

### estimateGas

• **estimateGas**: `Object`

Object that holds the functions that estimates the gas required for a given transaction.
Follows the pattern used by ethers.js.

#### Type declaration

| Name | Type |
| :------ | :------ |
| `deposit` | (`l1Token`: [`AddressLike`](../modules.md#addresslike), `l2Token`: [`AddressLike`](../modules.md#addresslike), `amount`: [`NumberLike`](../modules.md#numberlike), `opts?`: { `l2GasLimit?`: [`NumberLike`](../modules.md#numberlike) ; `overrides?`: `Overrides` ; `recipient?`: [`AddressLike`](../modules.md#addresslike)  }) => `Promise`<`BigNumber`\> |
| `withdraw` | (`l1Token`: [`AddressLike`](../modules.md#addresslike), `l2Token`: [`AddressLike`](../modules.md#addresslike), `amount`: [`NumberLike`](../modules.md#numberlike), `opts?`: { `overrides?`: `Overrides` ; `recipient?`: [`AddressLike`](../modules.md#addresslike)  }) => `Promise`<`BigNumber`\> |

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[estimateGas](../interfaces/IBridgeAdapter.md#estimategas)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:307](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L307)

___

### l1Bridge

• **l1Bridge**: `Contract`

L1 bridge contract.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[l1Bridge](../interfaces/IBridgeAdapter.md#l1bridge)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:26](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L26)

___

### l2Bridge

• **l2Bridge**: `Contract`

L2 bridge contract.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[l2Bridge](../interfaces/IBridgeAdapter.md#l2bridge)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:27](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L27)

___

### messenger

• **messenger**: [`ICrossChainMessenger`](../interfaces/ICrossChainMessenger.md)

Provider used to make queries related to cross-chain interactions.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[messenger](../interfaces/IBridgeAdapter.md#messenger)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:25](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L25)

___

### populateTransaction

• **populateTransaction**: `Object`

Object that holds the functions that generate transactions to be signed by the user.
Follows the pattern used by ethers.js.

#### Type declaration

| Name | Type |
| :------ | :------ |
| `deposit` | (`l1Token`: [`AddressLike`](../modules.md#addresslike), `l2Token`: [`AddressLike`](../modules.md#addresslike), `amount`: [`NumberLike`](../modules.md#numberlike), `opts?`: { `l2GasLimit?`: [`NumberLike`](../modules.md#numberlike) ; `overrides?`: `Overrides` ; `recipient?`: [`AddressLike`](../modules.md#addresslike)  }) => `Promise`<`TransactionRequest`\> |
| `withdraw` | (`l1Token`: [`AddressLike`](../modules.md#addresslike), `l2Token`: [`AddressLike`](../modules.md#addresslike), `amount`: [`NumberLike`](../modules.md#numberlike), `opts?`: { `overrides?`: `Overrides` ; `recipient?`: [`AddressLike`](../modules.md#addresslike)  }) => `Promise`<`TransactionRequest`\> |

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[populateTransaction](../interfaces/IBridgeAdapter.md#populatetransaction)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:236](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L236)

## Methods

### deposit

▸ **deposit**(`l1Token`, `l2Token`, `amount`, `signer`, `opts?`): `Promise`<`TransactionResponse`\>

Deposits some tokens into the L2 chain.

#### Parameters

| Name | Type |
| :------ | :------ |
| `l1Token` | [`AddressLike`](../modules.md#addresslike) |
| `l2Token` | [`AddressLike`](../modules.md#addresslike) |
| `amount` | [`NumberLike`](../modules.md#numberlike) |
| `signer` | `Signer` |
| `opts?` | `Object` |
| `opts.l2GasLimit?` | [`NumberLike`](../modules.md#numberlike) |
| `opts.overrides?` | `Overrides` |
| `opts.recipient?` | [`AddressLike`](../modules.md#addresslike) |

#### Returns

`Promise`<`TransactionResponse`\>

Transaction response for the deposit transaction.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[deposit](../interfaces/IBridgeAdapter.md#deposit)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:205](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L205)

___

### getDepositsByAddress

▸ **getDepositsByAddress**(`address`, `opts?`): `Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

Gets all deposits for a given address.

#### Parameters

| Name | Type |
| :------ | :------ |
| `address` | [`AddressLike`](../modules.md#addresslike) |
| `opts?` | `Object` |
| `opts.fromBlock?` | `BlockTag` |
| `opts.toBlock?` | `BlockTag` |

#### Returns

`Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

All deposit token bridge messages sent by the given address.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[getDepositsByAddress](../interfaces/IBridgeAdapter.md#getdepositsbyaddress)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:80](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L80)

___

### getTokenBridgeMessagesByAddress

▸ **getTokenBridgeMessagesByAddress**(`address`, `opts?`): `Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

Finds all cross chain messages that correspond to token deposits or withdrawals sent by a
particular address. Useful for finding deposits/withdrawals because the sender of the message
will appear to be the StandardBridge contract and not the actual end user.

#### Parameters

| Name | Type |
| :------ | :------ |
| `address` | [`AddressLike`](../modules.md#addresslike) |
| `opts?` | `Object` |
| `opts.direction?` | [`MessageDirection`](../enums/MessageDirection.md) |

#### Returns

`Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

All token bridge messages sent by the given address.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[getTokenBridgeMessagesByAddress](../interfaces/IBridgeAdapter.md#gettokenbridgemessagesbyaddress)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:55](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L55)

___

### getWithdrawalsByAddress

▸ **getWithdrawalsByAddress**(`address`, `opts?`): `Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

Gets all withdrawals for a given address.

#### Parameters

| Name | Type |
| :------ | :------ |
| `address` | [`AddressLike`](../modules.md#addresslike) |
| `opts?` | `Object` |
| `opts.fromBlock?` | `BlockTag` |
| `opts.toBlock?` | `BlockTag` |

#### Returns

`Promise`<[`TokenBridgeMessage`](../interfaces/TokenBridgeMessage.md)[]\>

All withdrawal token bridge messages sent by the given address.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[getWithdrawalsByAddress](../interfaces/IBridgeAdapter.md#getwithdrawalsbyaddress)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:123](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L123)

___

### supportsTokenPair

▸ **supportsTokenPair**(`l1Token`, `l2Token`): `Promise`<`boolean`\>

Checks whether the given token pair is supported by the bridge.

#### Parameters

| Name | Type |
| :------ | :------ |
| `l1Token` | [`AddressLike`](../modules.md#addresslike) |
| `l2Token` | [`AddressLike`](../modules.md#addresslike) |

#### Returns

`Promise`<`boolean`\>

Whether the given token pair is supported by the bridge.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[supportsTokenPair](../interfaces/IBridgeAdapter.md#supportstokenpair)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:162](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L162)

___

### withdraw

▸ **withdraw**(`l1Token`, `l2Token`, `amount`, `signer`, `opts?`): `Promise`<`TransactionResponse`\>

Withdraws some tokens back to the L1 chain.

#### Parameters

| Name | Type |
| :------ | :------ |
| `l1Token` | [`AddressLike`](../modules.md#addresslike) |
| `l2Token` | [`AddressLike`](../modules.md#addresslike) |
| `amount` | [`NumberLike`](../modules.md#numberlike) |
| `signer` | `Signer` |
| `opts?` | `Object` |
| `opts.overrides?` | `Overrides` |
| `opts.recipient?` | [`AddressLike`](../modules.md#addresslike) |

#### Returns

`Promise`<`TransactionResponse`\>

Transaction response for the withdraw transaction.

#### Implementation of

[IBridgeAdapter](../interfaces/IBridgeAdapter.md).[withdraw](../interfaces/IBridgeAdapter.md#withdraw)

#### Defined in

[packages/sdk/src/adapters/standard-bridge.ts:221](https://github.com/ethereum-optimism/optimism/blob/fe0376c5/packages/sdk/src/adapters/standard-bridge.ts#L221)
