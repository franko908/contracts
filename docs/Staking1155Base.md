# Staking1155Base





EXTENSION: Staking1155  The `Staking1155Base` smart contract implements NFT staking mechanism.  Allows users to stake their ERC-1155 NFTs and earn rewards in form of ERC-20 tokens.  Following features and implementation setup must be noted:      - ERC-1155 NFTs from only one collection can be staked.      - Contract admin can choose to give out rewards by either transferring or minting the rewardToken,        which is an ERC20 token. See {_mintRewards}.      - To implement custom logic for staking, reward calculation, etc. corresponding functions can be        overridden from the extension `Staking1155`.      - Ownership of the contract, with the ability to restrict certain functions to        only be called by the contract&#39;s owner.      - Multicall capability to perform multiple actions atomically.



## Methods

### claimRewards

```solidity
function claimRewards(uint256 _tokenId) external nonpayable
```

Claim accumulated rewards.

*See {_claimRewards}. Override that to implement custom logic.             See {_calculateRewards} for reward-calculation logic.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | Staked token Id. |

### contractURI

```solidity
function contractURI() external view returns (string)
```

Returns the contract metadata URI.




#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | string | undefined |

### getDefaultRewardsPerUnitTime

```solidity
function getDefaultRewardsPerUnitTime() external view returns (uint256 _rewardsPerUnitTime)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _rewardsPerUnitTime | uint256 | undefined |

### getDefaultTimeUnit

```solidity
function getDefaultTimeUnit() external view returns (uint256 _timeUnit)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _timeUnit | uint256 | undefined |

### getRewardTokenBalance

```solidity
function getRewardTokenBalance() external view returns (uint256 _rewardsAvailableInContract)
```

View total rewards available in the staking contract.




#### Returns

| Name | Type | Description |
|---|---|---|
| _rewardsAvailableInContract | uint256 | undefined |

### getRewardsPerUnitTime

```solidity
function getRewardsPerUnitTime(uint256 _tokenId) external view returns (uint256 _rewardsPerUnitTime)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _rewardsPerUnitTime | uint256 | undefined |

### getStakeInfo

```solidity
function getStakeInfo(address _staker) external view returns (uint256[] _tokensStaked, uint256[] _tokenAmounts, uint256 _totalRewards)
```

View all tokens staked and total rewards for a user.



#### Parameters

| Name | Type | Description |
|---|---|---|
| _staker | address | Address for which to calculated rewards. |

#### Returns

| Name | Type | Description |
|---|---|---|
| _tokensStaked | uint256[] |   List of token-ids staked. |
| _tokenAmounts | uint256[] |   Amount of each token-id staked. |
| _totalRewards | uint256 |   Total rewards available. |

### getStakeInfoForToken

```solidity
function getStakeInfoForToken(uint256 _tokenId, address _staker) external view returns (uint256 _tokensStaked, uint256 _rewards)
```

View amount staked and rewards for a user, for a given token-id.



#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | undefined |
| _staker | address | Address for which to calculated rewards. |

#### Returns

| Name | Type | Description |
|---|---|---|
| _tokensStaked | uint256 |   Amount of tokens staked for given token-id. |
| _rewards | uint256 |        Available reward amount. |

### getTimeUnit

```solidity
function getTimeUnit(uint256 _tokenId) external view returns (uint256 _timeUnit)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _timeUnit | uint256 | undefined |

### indexedTokens

```solidity
function indexedTokens(uint256) external view returns (uint256)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |

### isIndexed

```solidity
function isIndexed(uint256) external view returns (bool)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | bool | undefined |

### multicall

```solidity
function multicall(bytes[] data) external nonpayable returns (bytes[] results)
```

Receives and executes a batch of function calls on this contract.

*Receives and executes a batch of function calls on this contract.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| data | bytes[] | The bytes data that makes up the batch of function calls to execute. |

#### Returns

| Name | Type | Description |
|---|---|---|
| results | bytes[] | The bytes data that makes up the result of the batch of function calls executed. |

### owner

```solidity
function owner() external view returns (address)
```

Returns the owner of the contract.




#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### rewardToken

```solidity
function rewardToken() external view returns (address)
```



*ERC20 Reward Token address. See {_mintRewards} below.*


#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### setContractURI

```solidity
function setContractURI(string _uri) external nonpayable
```

Lets a contract admin set the URI for contract-level metadata.

*Caller should be authorized to setup contractURI, e.g. contract admin.                  See {_canSetContractURI}.                  Emits {ContractURIUpdated Event}.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _uri | string | keccak256 hash of the role. e.g. keccak256(&quot;TRANSFER_ROLE&quot;) |

### setDefaultRewardsPerUnitTime

```solidity
function setDefaultRewardsPerUnitTime(uint256 _defaultRewardsPerUnitTime) external nonpayable
```

Set rewards per unit of time.           Interpreted as x rewards per second/per day/etc based on time-unit.

*Only admin/authorized-account can call it.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _defaultRewardsPerUnitTime | uint256 | New rewards per unit time. |

### setDefaultTimeUnit

```solidity
function setDefaultTimeUnit(uint256 _defaultTimeUnit) external nonpayable
```

Set time unit. Set as a number of seconds.           Could be specified as -- x * 1 hours, x * 1 days, etc.

*Only admin/authorized-account can call it.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _defaultTimeUnit | uint256 | New time unit. |

### setOwner

```solidity
function setOwner(address _newOwner) external nonpayable
```

Lets an authorized wallet set a new owner for the contract.



#### Parameters

| Name | Type | Description |
|---|---|---|
| _newOwner | address | The address to set as the new owner of the contract. |

### setRewardsPerUnitTime

```solidity
function setRewardsPerUnitTime(uint256 _tokenId, uint256 _rewardsPerUnitTime) external nonpayable
```

Set rewards per unit of time.           Interpreted as x rewards per second/per day/etc based on time-unit.

*Only admin/authorized-account can call it.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | ERC1155 token Id. |
| _rewardsPerUnitTime | uint256 | New rewards per unit time. |

### setTimeUnit

```solidity
function setTimeUnit(uint256 _tokenId, uint256 _timeUnit) external nonpayable
```

Set time unit. Set as a number of seconds.           Could be specified as -- x * 1 hours, x * 1 days, etc.

*Only admin/authorized-account can call it.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | ERC1155 token Id. |
| _timeUnit | uint256 | New time unit. |

### stake

```solidity
function stake(uint256 _tokenId, uint256 _amount) external nonpayable
```

Stake ERC721 Tokens.

*See {_stake}. Override that to implement custom logic.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | ERC1155 token-id to stake. |
| _amount | uint256 | Amount to stake. |

### stakers

```solidity
function stakers(uint256, address) external view returns (uint256 amountStaked, uint256 timeOfLastUpdate, uint256 unclaimedRewards, uint256 conditionIdOflastUpdate)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |
| _1 | address | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| amountStaked | uint256 | undefined |
| timeOfLastUpdate | uint256 | undefined |
| unclaimedRewards | uint256 | undefined |
| conditionIdOflastUpdate | uint256 | undefined |

### stakersArray

```solidity
function stakersArray(uint256, uint256) external view returns (address)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _0 | uint256 | undefined |
| _1 | uint256 | undefined |

#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### stakingToken

```solidity
function stakingToken() external view returns (address)
```






#### Returns

| Name | Type | Description |
|---|---|---|
| _0 | address | undefined |

### withdraw

```solidity
function withdraw(uint256 _tokenId, uint256 _amount) external nonpayable
```

Withdraw staked tokens.

*See {_withdraw}. Override that to implement custom logic.*

#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId | uint256 | ERC1155 token-id to withdraw. |
| _amount | uint256 | Amount to withdraw. |



## Events

### ContractURIUpdated

```solidity
event ContractURIUpdated(string prevURI, string newURI)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| prevURI  | string | undefined |
| newURI  | string | undefined |

### OwnerUpdated

```solidity
event OwnerUpdated(address indexed prevOwner, address indexed newOwner)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| prevOwner `indexed` | address | undefined |
| newOwner `indexed` | address | undefined |

### RewardsClaimed

```solidity
event RewardsClaimed(address indexed staker, uint256 rewardAmount)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| staker `indexed` | address | undefined |
| rewardAmount  | uint256 | undefined |

### TokensStaked

```solidity
event TokensStaked(address indexed staker, uint256 indexed tokenId, uint256 amount)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| staker `indexed` | address | undefined |
| tokenId `indexed` | uint256 | undefined |
| amount  | uint256 | undefined |

### TokensWithdrawn

```solidity
event TokensWithdrawn(address indexed staker, uint256 indexed tokenId, uint256 amount)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| staker `indexed` | address | undefined |
| tokenId `indexed` | uint256 | undefined |
| amount  | uint256 | undefined |

### UpdatedDefaultRewardsPerUnitTime

```solidity
event UpdatedDefaultRewardsPerUnitTime(uint256 oldRewardsPerUnitTime, uint256 newRewardsPerUnitTime)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| oldRewardsPerUnitTime  | uint256 | undefined |
| newRewardsPerUnitTime  | uint256 | undefined |

### UpdatedDefaultTimeUnit

```solidity
event UpdatedDefaultTimeUnit(uint256 oldTimeUnit, uint256 newTimeUnit)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| oldTimeUnit  | uint256 | undefined |
| newTimeUnit  | uint256 | undefined |

### UpdatedRewardsPerUnitTime

```solidity
event UpdatedRewardsPerUnitTime(uint256 indexed _tokenId, uint256 oldRewardsPerUnitTime, uint256 newRewardsPerUnitTime)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId `indexed` | uint256 | undefined |
| oldRewardsPerUnitTime  | uint256 | undefined |
| newRewardsPerUnitTime  | uint256 | undefined |

### UpdatedTimeUnit

```solidity
event UpdatedTimeUnit(uint256 indexed _tokenId, uint256 oldTimeUnit, uint256 newTimeUnit)
```





#### Parameters

| Name | Type | Description |
|---|---|---|
| _tokenId `indexed` | uint256 | undefined |
| oldTimeUnit  | uint256 | undefined |
| newTimeUnit  | uint256 | undefined |



