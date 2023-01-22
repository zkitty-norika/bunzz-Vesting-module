# WRITE(main)

## connectToOtherContracts
~~Connect the underlying pair from dex and the dex router~~
Initial setup to connect the module to ERC20 being vested.

- Who can call: ContractOwner

|Name|Type|Description|Example|Default|
|--- |---|---|---|---|
|token|address[]|The address of the token that will be vested|[0x690b9a9e9aa1c9db991c7721a92d351db4fac990]|N/A|

## createVestingSchedule

- Who can call: ContractOwner

|Name|Type|Unit|Description|Example|Default|
|--- |---|---|---|---|---|
|_beneficiary|address|account's address|the address of the beneficiary|0x690b9a9e9aa1c9db991c7721a92d351db4fac990|N/A|
|_start|uint256|unix timestamp in seconds|the start datetime|1674396730(January 22, 2023 2:12:10 PM)|N/A|
|_cliff|uint256|unix timestamp|the pause between the start time and the moment of available withdrawal|1674396730|N/A|
|_duration|uint256|duration of unix timestamp in seconds|the duration of the vesting schedule|1674396730|N/A|
|_slicePerSeconds|uint256|token unit|how many tokens will be unlocked every second starting with the startTime.|10|N/A|
|_revocable|boolean|--|a boolean that gives the owner the power to revoke the vesting schedule or not. This can only be decided when the vesting schedule is created.|true|false|
|_amount|uint256|token unit|how many tokens will be unlocked every second starting with the startTime.|10|0|

## revoke

Owner can only revoke a vesting schedule that have been marked as revocable at the moment of creation.

- Who can call: ContractOwner

|Name|Type|Description|Example|Default|
|---|---|---|---|---|
||bytes32|||

## release

- Who can call: ContractOwner, Beneficiary determined in the vestingSchedule

|Name|Type|Description|Example|Default|
|---|---|---|---|---|




# WRITE(emergency case)
- transferOwnership
- renounceOwnership