---
id: 'SequencerProvider'
title: 'Class: SequencerProvider'
sidebar_label: 'SequencerProvider'
sidebar_position: 0
custom_edit_url: null
---

## Implements

- [`ProviderInterface`](ProviderInterface.md)

## Constructors

### constructor

• **new SequencerProvider**(`optionsOrProvider?`)

#### Parameters

| Name                | Type                                                                          | Default value    |
| :------------------ | :---------------------------------------------------------------------------- | :--------------- |
| `optionsOrProvider` | [`SequencerProviderOptions`](../namespaces/types.md#sequencerprovideroptions) | `defaultOptions` |

#### Defined in

[src/provider/sequencer.ts:91](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L91)

## Properties

### baseUrl

• **baseUrl**: `string`

#### Defined in

[src/provider/sequencer.ts:77](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L77)

---

### feederGatewayUrl

• **feederGatewayUrl**: `string`

#### Defined in

[src/provider/sequencer.ts:79](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L79)

---

### gatewayUrl

• **gatewayUrl**: `string`

#### Defined in

[src/provider/sequencer.ts:81](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L81)

---

### headers

• `Optional` **headers**: `Record`<`string`, `string`\>

#### Defined in

[src/provider/sequencer.ts:83](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L83)

---

### blockIdentifier

• `Private` **blockIdentifier**: [`BlockIdentifier`](../namespaces/types.md#blockidentifier)

#### Defined in

[src/provider/sequencer.ts:85](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L85)

---

### chainId

• `Private` **chainId**: [`StarknetChainId`](../enums/constants.StarknetChainId.md)

#### Defined in

[src/provider/sequencer.ts:87](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L87)

---

### responseParser

• `Private` **responseParser**: `SequencerAPIResponseParser`

#### Defined in

[src/provider/sequencer.ts:89](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L89)

## Methods

### getNetworkFromName

▸ `Static` `Protected` **getNetworkFromName**(`name`): `BaseUrl`

#### Parameters

| Name   | Type                                                                                                             |
| :----- | :--------------------------------------------------------------------------------------------------------------- |
| `name` | [`StarknetChainId`](../enums/constants.StarknetChainId.md) \| [`NetworkName`](../enums/constants.NetworkName.md) |

#### Returns

`BaseUrl`

#### Defined in

[src/provider/sequencer.ts:111](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L111)

---

### getChainIdFromBaseUrl

▸ `Static` `Protected` **getChainIdFromBaseUrl**(`baseUrl`): [`StarknetChainId`](../enums/constants.StarknetChainId.md)

#### Parameters

| Name      | Type     |
| :-------- | :------- |
| `baseUrl` | `string` |

#### Returns

[`StarknetChainId`](../enums/constants.StarknetChainId.md)

#### Defined in

[src/provider/sequencer.ts:124](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L124)

---

### getFetchUrl

▸ `Private` **getFetchUrl**(`endpoint`): `string`

#### Parameters

| Name       | Type                                                            |
| :--------- | :-------------------------------------------------------------- |
| `endpoint` | keyof [`Endpoints`](../namespaces/types.Sequencer.md#endpoints) |

#### Returns

`string`

#### Defined in

[src/provider/sequencer.ts:138](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L138)

---

### getFetchMethod

▸ `Private` **getFetchMethod**(`endpoint`): `"POST"` \| `"GET"`

#### Parameters

| Name       | Type                                                            |
| :--------- | :-------------------------------------------------------------- |
| `endpoint` | keyof [`Endpoints`](../namespaces/types.Sequencer.md#endpoints) |

#### Returns

`"POST"` \| `"GET"`

#### Defined in

[src/provider/sequencer.ts:143](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L143)

---

### getQueryString

▸ `Private` **getQueryString**(`query?`): `string`

#### Parameters

| Name     | Type                       |
| :------- | :------------------------- |
| `query?` | `Record`<`string`, `any`\> |

#### Returns

`string`

#### Defined in

[src/provider/sequencer.ts:156](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L156)

---

### getHeaders

▸ `Private` **getHeaders**(`method`): `undefined` \| `Record`<`string`, `string`\>

#### Parameters

| Name     | Type                                                                |
| :------- | :------------------------------------------------------------------ |
| `method` | [`SequencerHttpMethod`](../namespaces/types.md#sequencerhttpmethod) |

#### Returns

`undefined` \| `Record`<`string`, `string`\>

#### Defined in

[src/provider/sequencer.ts:173](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L173)

---

### fetchEndpoint

▸ `Protected` **fetchEndpoint**<`T`\>(`endpoint`, `...«destructured»`): `Promise`<[`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"RESPONSE"``]\>

#### Type parameters

| Name | Type                                                                    |
| :--- | :---------------------------------------------------------------------- |
| `T`  | extends keyof [`Endpoints`](../namespaces/types.Sequencer.md#endpoints) |

#### Parameters

| Name                | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| :------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `endpoint`          | `T`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `...«destructured»` | [`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"QUERY"``] extends `never` ? [`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"REQUEST"``] extends `never` ? [] : [`undefined`, [`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"REQUEST"``]] : [`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"REQUEST"``] extends `never` ? [[`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"QUERY"``]] : [[`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"QUERY"``], [`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"REQUEST"``]] |

#### Returns

`Promise`<[`Endpoints`](../namespaces/types.Sequencer.md#endpoints)[`T`][``"RESPONSE"``]\>

#### Defined in

[src/provider/sequencer.ts:184](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L184)

---

### fetch

▸ **fetch**(`endpoint`, `options?`): `Promise`<`any`\>

#### Parameters

| Name                           | Type                                                                |
| :----------------------------- | :------------------------------------------------------------------ |
| `endpoint`                     | `string`                                                            |
| `options?`                     | `Object`                                                            |
| `options.method?`              | [`SequencerHttpMethod`](../namespaces/types.md#sequencerhttpmethod) |
| `options.body?`                | `any`                                                               |
| `options.parseAlwaysAsBigInt?` | `boolean`                                                           |

#### Returns

`Promise`<`any`\>

#### Defined in

[src/provider/sequencer.ts:206](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L206)

---

### getChainId

▸ **getChainId**(): `Promise`<[`StarknetChainId`](../enums/constants.StarknetChainId.md)\>

Gets the Starknet chain Id

#### Returns

`Promise`<[`StarknetChainId`](../enums/constants.StarknetChainId.md)\>

the chain Id

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getChainId](ProviderInterface.md#getchainid)

#### Defined in

[src/provider/sequencer.ts:247](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L247)

---

### callContract

▸ **callContract**(`«destructured»`, `blockIdentifier?`): `Promise`<[`CallContractResponse`](../namespaces/types.md#callcontractresponse)\>

Calls a function on the Starknet contract.

#### Parameters

| Name              | Type                                                        | Description              |
| :---------------- | :---------------------------------------------------------- | :----------------------- |
| `«destructured»`  | [`Call`](../namespaces/types.md#call)                       | transaction to be called |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier         |

#### Returns

`Promise`<[`CallContractResponse`](../namespaces/types.md#callcontractresponse)\>

the result of the function on the smart contract.

#### Implementation of

[ProviderInterface](ProviderInterface.md).[callContract](ProviderInterface.md#callcontract)

#### Defined in

[src/provider/sequencer.ts:251](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L251)

---

### getBlock

▸ **getBlock**(`blockIdentifier?`): `Promise`<[`GetBlockResponse`](../interfaces/types.GetBlockResponse.md)\>

Gets the block information

#### Parameters

| Name              | Type                                                        | Description      |
| :---------------- | :---------------------------------------------------------- | :--------------- |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier |

#### Returns

`Promise`<[`GetBlockResponse`](../interfaces/types.GetBlockResponse.md)\>

the block object

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getBlock](ProviderInterface.md#getblock)

#### Defined in

[src/provider/sequencer.ts:269](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L269)

---

### getNonceForAddress

▸ **getNonceForAddress**(`contractAddress`, `blockIdentifier?`): `Promise`<`string`\>

Gets the nonce of a contract with respect to a specific block

#### Parameters

| Name              | Type                                                        | Description      |
| :---------------- | :---------------------------------------------------------- | :--------------- |
| `contractAddress` | `string`                                                    | contract address |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | -                |

#### Returns

`Promise`<`string`\>

the hex nonce

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getNonceForAddress](ProviderInterface.md#getnonceforaddress)

#### Defined in

[src/provider/sequencer.ts:277](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L277)

---

### getStorageAt

▸ **getStorageAt**(`contractAddress`, `key`, `blockIdentifier?`): `Promise`<`string`\>

Gets the contract's storage variable at a specific key.

#### Parameters

| Name              | Type                                                        | Description                                                |
| :---------------- | :---------------------------------------------------------- | :--------------------------------------------------------- |
| `contractAddress` | `string`                                                    |                                                            |
| `key`             | [`BigNumberish`](../namespaces/types.md#bignumberish)       | from getStorageVarAddress('<STORAGE_VARIABLE_NAME>') (WIP) |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier                                           |

#### Returns

`Promise`<`string`\>

the value of the storage variable

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getStorageAt](ProviderInterface.md#getstorageat)

#### Defined in

[src/provider/sequencer.ts:284](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L284)

---

### getTransaction

▸ **getTransaction**(`txHash`): `Promise`<[`GetTransactionResponse`](../namespaces/types.md#gettransactionresponse)\>

Gets the transaction information from a tx id.

#### Parameters

| Name     | Type                                                  |
| :------- | :---------------------------------------------------- |
| `txHash` | [`BigNumberish`](../namespaces/types.md#bignumberish) |

#### Returns

`Promise`<[`GetTransactionResponse`](../namespaces/types.md#gettransactionresponse)\>

the transaction object { transaction_id, status, transaction, block_number?, block_number?, transaction_index?, transaction_failure_reason? }

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getTransaction](ProviderInterface.md#gettransaction)

#### Defined in

[src/provider/sequencer.ts:297](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L297)

---

### getTransactionReceipt

▸ **getTransactionReceipt**(`txHash`): `Promise`<[`GetTransactionReceiptResponse`](../namespaces/types.md#gettransactionreceiptresponse)\>

Gets the transaction receipt from a tx hash.

#### Parameters

| Name     | Type                                                  |
| :------- | :---------------------------------------------------- |
| `txHash` | [`BigNumberish`](../namespaces/types.md#bignumberish) |

#### Returns

`Promise`<[`GetTransactionReceiptResponse`](../namespaces/types.md#gettransactionreceiptresponse)\>

the transaction receipt object

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getTransactionReceipt](ProviderInterface.md#gettransactionreceipt)

#### Defined in

[src/provider/sequencer.ts:306](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L306)

---

### getClassAt

▸ **getClassAt**(`contractAddress`, `blockIdentifier?`): `Promise`<[`ContractClassResponse`](../namespaces/types.md#contractclassresponse)\>

Gets the contract class of the deployed contract.

#### Parameters

| Name              | Type                                                        | Description      |
| :---------------- | :---------------------------------------------------------- | :--------------- |
| `contractAddress` | `string`                                                    | contract address |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier |

#### Returns

`Promise`<[`ContractClassResponse`](../namespaces/types.md#contractclassresponse)\>

Contract class of compiled contract

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getClassAt](ProviderInterface.md#getclassat)

#### Defined in

[src/provider/sequencer.ts:313](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L313)

---

### getClassHashAt

▸ **getClassHashAt**(`contractAddress`, `blockIdentifier?`): `Promise`<`string`\>

Returns the class hash deployed under the given address.

#### Parameters

| Name              | Type                                                        | Description      |
| :---------------- | :---------------------------------------------------------- | :--------------- |
| `contractAddress` | `string`                                                    | contract address |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier |

#### Returns

`Promise`<`string`\>

Class hash

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getClassHashAt](ProviderInterface.md#getclasshashat)

#### Defined in

[src/provider/sequencer.ts:322](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L322)

---

### getClassByHash

▸ **getClassByHash**(`classHash`, `blockIdentifier?`): `Promise`<[`ContractClassResponse`](../namespaces/types.md#contractclassresponse)\>

Returns the contract class deployed under the given class hash.

#### Parameters

| Name              | Type                                                        | Description |
| :---------------- | :---------------------------------------------------------- | :---------- |
| `classHash`       | `string`                                                    | class hash  |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | -           |

#### Returns

`Promise`<[`ContractClassResponse`](../namespaces/types.md#contractclassresponse)\>

Contract class of compiled contract

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getClassByHash](ProviderInterface.md#getclassbyhash)

#### Defined in

[src/provider/sequencer.ts:329](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L329)

---

### getCompiledClassByClassHash

▸ **getCompiledClassByClassHash**(`classHash`, `blockIdentifier?`): `Promise`<[`CairoAssembly`](../namespaces/types.md#cairoassembly)\>

#### Parameters

| Name              | Type                                                        |
| :---------------- | :---------------------------------------------------------- |
| `classHash`       | `string`                                                    |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) |

#### Returns

`Promise`<[`CairoAssembly`](../namespaces/types.md#cairoassembly)\>

#### Defined in

[src/provider/sequencer.ts:338](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L338)

---

### invokeFunction

▸ **invokeFunction**(`functionInvocation`, `details`): `Promise`<[`InvokeFunctionResponse`](../interfaces/types.InvokeFunctionResponse.md)\>

Invokes a function on starknet

**`Deprecated`**

This method wont be supported as soon as fees are mandatory. Should not be used outside of Account class

#### Parameters

| Name                 | Type                                                                                | Description                                                                                                                                                                                                             |
| :------------------- | :---------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `functionInvocation` | [`Invocation`](../namespaces/types.md#invocation)                                   | the invocation object containing: - contractAddress - the address of the contract - entrypoint - the entrypoint of the contract - calldata - (defaults to []) the calldata - signature - (defaults to []) the signature |
| `details`            | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce) | optional details containing: - nonce - optional nonce - version - optional version - maxFee - optional maxFee                                                                                                           |

#### Returns

`Promise`<[`InvokeFunctionResponse`](../interfaces/types.InvokeFunctionResponse.md)\>

response from addTransaction

#### Implementation of

[ProviderInterface](ProviderInterface.md).[invokeFunction](ProviderInterface.md#invokefunction)

#### Defined in

[src/provider/sequencer.ts:345](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L345)

---

### deployAccountContract

▸ **deployAccountContract**(`«destructured»`, `details`): `Promise`<[`DeployContractResponse`](../interfaces/types.DeployContractResponse.md)\>

Deploys a given compiled Account contract (json) to starknet

#### Parameters

| Name             | Type                                                                                          | Description                                                                                       |
| :--------------- | :-------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------ |
| `«destructured»` | [`DeployAccountContractTransaction`](../namespaces/types.md#deployaccountcontracttransaction) | payload to be deployed containing: - compiled contract code - constructor calldata - address salt |
| `details`        | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce)           | -                                                                                                 |

#### Returns

`Promise`<[`DeployContractResponse`](../interfaces/types.DeployContractResponse.md)\>

a confirmation of sending a transaction on the starknet contract

#### Implementation of

[ProviderInterface](ProviderInterface.md).[deployAccountContract](ProviderInterface.md#deployaccountcontract)

#### Defined in

[src/provider/sequencer.ts:360](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L360)

---

### declareContract

▸ **declareContract**(`«destructured»`, `details`): `Promise`<[`DeclareContractResponse`](../interfaces/types.DeclareContractResponse.md)\>

Declares a given compiled contract (json) to starknet

#### Parameters

| Name             | Type                                                                                | Description                                                                                          |
| :--------------- | :---------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------- |
| `«destructured»` | [`DeclareContractTransaction`](../namespaces/types.md#declarecontracttransaction)   | transaction payload to be deployed containing: - compiled contract code - sender address - signature |
| `details`        | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce) | Invocation Details containing: - nonce - optional version - optional maxFee                          |

#### Returns

`Promise`<[`DeclareContractResponse`](../interfaces/types.DeclareContractResponse.md)\>

a confirmation of sending a transaction on the starknet contract

#### Implementation of

[ProviderInterface](ProviderInterface.md).[declareContract](ProviderInterface.md#declarecontract)

#### Defined in

[src/provider/sequencer.ts:376](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L376)

---

### getEstimateFee

▸ **getEstimateFee**(`invocation`, `invocationDetails`, `blockIdentifier?`, `skipValidate?`): `Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

Estimates the fee for a given INVOKE transaction

**`Deprecated`**

Please use getInvokeEstimateFee or getDeclareEstimateFee instead. Should not be used outside of Account class

#### Parameters

| Name                | Type                                                                                | Default value | Description                                                                                                                                                                                                             |
| :------------------ | :---------------------------------------------------------------------------------- | :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `invocation`        | [`Invocation`](../namespaces/types.md#invocation)                                   | `undefined`   | the invocation object containing: - contractAddress - the address of the contract - entrypoint - the entrypoint of the contract - calldata - (defaults to []) the calldata - signature - (defaults to []) the signature |
| `invocationDetails` | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce) | `undefined`   | optional details containing: - nonce - optional nonce - version - optional version                                                                                                                                      |
| `blockIdentifier`   | [`BlockIdentifier`](../namespaces/types.md#blockidentifier)                         | `undefined`   | (optional) block identifier                                                                                                                                                                                             |
| `skipValidate`      | `boolean`                                                                           | `false`       | (optional) skip cairo **validate** method                                                                                                                                                                               |

#### Returns

`Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

the estimated fee

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getEstimateFee](ProviderInterface.md#getestimatefee)

#### Defined in

[src/provider/sequencer.ts:404](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L404)

---

### getInvokeEstimateFee

▸ **getInvokeEstimateFee**(`invocation`, `invocationDetails`, `blockIdentifier?`, `skipValidate?`): `Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

Estimates the fee for a given INVOKE transaction

#### Parameters

| Name                | Type                                                                                | Default value | Description                                                                                                                                                                                                             |
| :------------------ | :---------------------------------------------------------------------------------- | :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `invocation`        | [`Invocation`](../namespaces/types.md#invocation)                                   | `undefined`   | the invocation object containing: - contractAddress - the address of the contract - entrypoint - the entrypoint of the contract - calldata - (defaults to []) the calldata - signature - (defaults to []) the signature |
| `invocationDetails` | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce) | `undefined`   | optional details containing: - nonce - optional nonce - version - optional version                                                                                                                                      |
| `blockIdentifier`   | [`BlockIdentifier`](../namespaces/types.md#blockidentifier)                         | `undefined`   | (optional) block identifier                                                                                                                                                                                             |
| `skipValidate`      | `boolean`                                                                           | `false`       | (optional) skip cairo **validate** method                                                                                                                                                                               |

#### Returns

`Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

the estimated fee

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getInvokeEstimateFee](ProviderInterface.md#getinvokeestimatefee)

#### Defined in

[src/provider/sequencer.ts:413](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L413)

---

### getDeclareEstimateFee

▸ **getDeclareEstimateFee**(`invocation`, `details`, `blockIdentifier?`, `skipValidate?`): `Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

Estimates the fee for a given DECLARE transaction

#### Parameters

| Name              | Type                                                                                | Default value | Description                                                                                                                           |
| :---------------- | :---------------------------------------------------------------------------------- | :------------ | :------------------------------------------------------------------------------------------------------------------------------------ |
| `invocation`      | [`DeclareContractTransaction`](../namespaces/types.md#declarecontracttransaction)   | `undefined`   | transaction payload to be declared containing: - compiled contract code - sender address - signature - (defaults to []) the signature |
| `details`         | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce) | `undefined`   | optional details containing: - nonce - version - optional version - optional maxFee                                                   |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier)                         | `undefined`   | (optional) block identifier                                                                                                           |
| `skipValidate`    | `boolean`                                                                           | `false`       | (optional) skip cairo **validate** method                                                                                             |

#### Returns

`Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

the estimated fee

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getDeclareEstimateFee](ProviderInterface.md#getdeclareestimatefee)

#### Defined in

[src/provider/sequencer.ts:432](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L432)

---

### getDeployAccountEstimateFee

▸ **getDeployAccountEstimateFee**(`invocation`, `details`, `blockIdentifier?`, `skipValidate?`): `Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

Estimates the fee for a given DEPLOY_ACCOUNT transaction

#### Parameters

| Name              | Type                                                                                          | Default value | Description                                                                                                                                 |
| :---------------- | :-------------------------------------------------------------------------------------------- | :------------ | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `invocation`      | [`DeployAccountContractTransaction`](../namespaces/types.md#deployaccountcontracttransaction) | `undefined`   | transaction payload to be deployed containing: - classHash - constructorCalldata - addressSalt - signature - (defaults to []) the signature |
| `details`         | [`InvocationsDetailsWithNonce`](../namespaces/types.md#invocationsdetailswithnonce)           | `undefined`   | optional details containing: - nonce - version - optional version - optional maxFee                                                         |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier)                                   | `undefined`   | (optional) block identifier                                                                                                                 |
| `skipValidate`    | `boolean`                                                                                     | `false`       | (optional) skip cairo **validate** method                                                                                                   |

#### Returns

`Promise`<[`EstimateFeeResponse`](../interfaces/types.EstimateFeeResponse.md)\>

the estimated fee

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getDeployAccountEstimateFee](ProviderInterface.md#getdeployaccountestimatefee)

#### Defined in

[src/provider/sequencer.ts:451](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L451)

---

### getEstimateFeeBulk

▸ **getEstimateFeeBulk**(`invocations`, `«destructured»`): `Promise`<[`EstimateFeeResponseBulk`](../namespaces/types.md#estimatefeeresponsebulk)\>

Estimates the fee for a list of INVOKE transaction

#### Parameters

| Name             | Type                                                                            | Description                                                                                                                  |
| :--------------- | :------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------- |
| `invocations`    | [`AccountInvocations`](../namespaces/types.md#accountinvocations)               | AccountInvocations - Complete invocations array with account details                                                         |
| `«destructured»` | [`getEstimateFeeBulkOptions`](../namespaces/types.md#getestimatefeebulkoptions) | getEstimateFeeBulkOptions - (optional) blockIdentifier - BlockIdentifier - (optional) skipValidate - boolean (default false) |

#### Returns

`Promise`<[`EstimateFeeResponseBulk`](../namespaces/types.md#estimatefeeresponsebulk)\>

the estimated fee

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getEstimateFeeBulk](ProviderInterface.md#getestimatefeebulk)

#### Defined in

[src/provider/sequencer.ts:470](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L470)

---

### getCode

▸ **getCode**(`contractAddress`, `blockIdentifier?`): `Promise`<[`GetCodeResponse`](../namespaces/types.Sequencer.md#getcoderesponse)\>

**`Deprecated`**

The method should not be used

#### Parameters

| Name              | Type                                                        |
| :---------------- | :---------------------------------------------------------- |
| `contractAddress` | `string`                                                    |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) |

#### Returns

`Promise`<[`GetCodeResponse`](../namespaces/types.Sequencer.md#getcoderesponse)\>

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getCode](ProviderInterface.md#getcode)

#### Defined in

[src/provider/sequencer.ts:482](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L482)

---

### waitForTransaction

▸ **waitForTransaction**(`txHash`, `options?`): `Promise`<[`GetTransactionReceiptResponse`](../namespaces/types.md#gettransactionreceiptresponse)\>

Wait for the transaction to be accepted

#### Parameters

| Name       | Type                                                                            | Description                                                                                                                              |
| :--------- | :------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `txHash`   | [`BigNumberish`](../namespaces/types.md#bignumberish)                           | transaction hash                                                                                                                         |
| `options?` | [`waitForTransactionOptions`](../namespaces/types.md#waitfortransactionoptions) | waitForTransactionOptions - (optional) retryInterval: number \| undefined; - (optional) successStates: TransactionStatus[] \| undefined; |

#### Returns

`Promise`<[`GetTransactionReceiptResponse`](../namespaces/types.md#gettransactionreceiptresponse)\>

GetTransactionReceiptResponse

#### Implementation of

[ProviderInterface](ProviderInterface.md).[waitForTransaction](ProviderInterface.md#waitfortransaction)

#### Defined in

[src/provider/sequencer.ts:489](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L489)

---

### getTransactionStatus

▸ **getTransactionStatus**(`txHash`): `Promise`<[`GetTransactionStatusResponse`](../namespaces/types.md#gettransactionstatusresponse)\>

Gets the status of a transaction.

#### Parameters

| Name     | Type                                                  | Description  |
| :------- | :---------------------------------------------------- | :----------- |
| `txHash` | [`BigNumberish`](../namespaces/types.md#bignumberish) | BigNumberish |

#### Returns

`Promise`<[`GetTransactionStatusResponse`](../namespaces/types.md#gettransactionstatusresponse)\>

GetTransactionStatusResponse - the transaction status object

#### Defined in

[src/provider/sequencer.ts:544](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L544)

---

### getContractAddresses

▸ **getContractAddresses**(): `Promise`<[`GetContractAddressesResponse`](../namespaces/types.md#getcontractaddressesresponse)\>

Gets the smart contract address on the goerli testnet.

#### Returns

`Promise`<[`GetContractAddressesResponse`](../namespaces/types.md#getcontractaddressesresponse)\>

GetContractAddressesResponse - starknet smart contract addresses

#### Defined in

[src/provider/sequencer.ts:553](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L553)

---

### getTransactionTrace

▸ **getTransactionTrace**(`txHash`): `Promise`<[`TransactionTraceResponse`](../namespaces/types.Sequencer.md#transactiontraceresponse)\>

Gets the transaction trace from a tx id.

#### Parameters

| Name     | Type                                                  | Description  |
| :------- | :---------------------------------------------------- | :----------- |
| `txHash` | [`BigNumberish`](../namespaces/types.md#bignumberish) | BigNumberish |

#### Returns

`Promise`<[`TransactionTraceResponse`](../namespaces/types.Sequencer.md#transactiontraceresponse)\>

TransactionTraceResponse - the transaction trace

#### Defined in

[src/provider/sequencer.ts:562](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L562)

---

### estimateMessageFee

▸ **estimateMessageFee**(`«destructured»`, `blockIdentifier?`): `Promise`<[`EstimateFeeResponse`](../namespaces/types.Sequencer.md#estimatefeeresponse)\>

#### Parameters

| Name              | Type                                                        |
| :---------------- | :---------------------------------------------------------- |
| `«destructured»`  | [`CallL1Handler`](../namespaces/types.md#calll1handler)     |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) |

#### Returns

`Promise`<[`EstimateFeeResponse`](../namespaces/types.Sequencer.md#estimatefeeresponse)\>

#### Defined in

[src/provider/sequencer.ts:569](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L569)

---

### getSimulateTransaction

▸ **getSimulateTransaction**(`invocations`, `«destructured»`): `Promise`<[`SimulateTransactionResponse`](../namespaces/types.md#simulatetransactionresponse)\>

Simulate transaction using Sequencer provider
WARNING!: Sequencer will process only first element from invocations array

#### Parameters

| Name             | Type                                                                                    | Description                                                       |
| :--------------- | :-------------------------------------------------------------------------------------- | :---------------------------------------------------------------- |
| `invocations`    | [`AccountInvocations`](../namespaces/types.md#accountinvocations)                       | Array of invocations, but only first invocation will be processed |
| `«destructured»` | [`getSimulateTransactionOptions`](../namespaces/types.md#getsimulatetransactionoptions) | -                                                                 |

#### Returns

`Promise`<[`SimulateTransactionResponse`](../namespaces/types.md#simulatetransactionresponse)\>

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getSimulateTransaction](ProviderInterface.md#getsimulatetransaction)

#### Defined in

[src/provider/sequencer.ts:592](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L592)

---

### getStateUpdate

▸ **getStateUpdate**(`blockIdentifier?`): `Promise`<[`StateUpdateResponse`](../interfaces/types.StateUpdateResponse.md)\>

Gets the state changes in a specific block

#### Parameters

| Name              | Type                                                        | Description      |
| :---------------- | :---------------------------------------------------------- | :--------------- |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) | block identifier |

#### Returns

`Promise`<[`StateUpdateResponse`](../interfaces/types.StateUpdateResponse.md)\>

StateUpdateResponse

#### Implementation of

[ProviderInterface](ProviderInterface.md).[getStateUpdate](ProviderInterface.md#getstateupdate)

#### Defined in

[src/provider/sequencer.ts:619](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L619)

---

### getBlockTraces

▸ **getBlockTraces**(`blockIdentifier?`): `Promise`<[`BlockTransactionTracesResponse`](../namespaces/types.Sequencer.md#blocktransactiontracesresponse)\>

#### Parameters

| Name              | Type                                                        |
| :---------------- | :---------------------------------------------------------- |
| `blockIdentifier` | [`BlockIdentifier`](../namespaces/types.md#blockidentifier) |

#### Returns

`Promise`<[`BlockTransactionTracesResponse`](../namespaces/types.Sequencer.md#blocktransactiontracesresponse)\>

#### Defined in

[src/provider/sequencer.ts:629](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L629)

---

### getStarkName

▸ **getStarkName**(`address`, `StarknetIdContract?`): `Promise`<`string`\>

#### Parameters

| Name                  | Type                                                  |
| :-------------------- | :---------------------------------------------------- |
| `address`             | [`BigNumberish`](../namespaces/types.md#bignumberish) |
| `StarknetIdContract?` | `string`                                              |

#### Returns

`Promise`<`string`\>

#### Defined in

[src/provider/sequencer.ts:636](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L636)

---

### getAddressFromStarkName

▸ **getAddressFromStarkName**(`name`, `StarknetIdContract?`): `Promise`<`string`\>

#### Parameters

| Name                  | Type     |
| :-------------------- | :------- |
| `name`                | `string` |
| `StarknetIdContract?` | `string` |

#### Returns

`Promise`<`string`\>

#### Defined in

[src/provider/sequencer.ts:640](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L640)

---

### buildTransaction

▸ **buildTransaction**(`invocation`, `versionType?`): [`AccountTransactionItem`](../namespaces/types.Sequencer.md#accounttransactionitem)

Build Single AccountTransaction from Single AccountInvocation

#### Parameters

| Name           | Type                                                                    | Description                                                 |
| :------------- | :---------------------------------------------------------------------- | :---------------------------------------------------------- |
| `invocation`   | [`AccountInvocationItem`](../namespaces/types.md#accountinvocationitem) | AccountInvocationItem                                       |
| `versionType?` | `"fee"` \| `"transaction"`                                              | 'fee' \| 'transaction' - used to determine default versions |

#### Returns

[`AccountTransactionItem`](../namespaces/types.Sequencer.md#accounttransactionitem)

AccountTransactionItem

#### Defined in

[src/provider/sequencer.ts:650](https://github.com/0xs34n/starknet.js/blob/develop/src/provider/sequencer.ts#L650)
