<div id="splash">
    <div id="project">
          <span class="splash-title">
               Project
          </span>
          <br />
          <span id="project-value">
               Sigma Comittee
          </span>
    </div>
     <div id="details">
          <div id="left">
               <span class="splash-title">
                    Client
               </span>
               <br />
               <span class="details-value">
                    Indexed Finance
               </span>
               <br />
               <span class="splash-title">
                    Date
               </span>
               <br />
               <span class="details-value">
                    February 2021
               </span>
          </div>
          <div id="right">
               <span class="splash-title">
                    Reviewers
               </span>
               <br />
               <span class="details-value">
                    Daniel Luca
               </span><br />
               <span class="contact">@cleanunicorn</span>
               <br />
               <span class="details-value">
                    Andrei Simion
               </span><br />
               <span class="contact">@andreiashu</span>
          </div>
    </div>
</div>

## Table of Contents
 - [Details](#details)
 - [Issues Summary](#issues-summary)
 - [Executive summary](#executive-summary)
     - [Day 1](#day-1)
     - [Day 2](#day-2)
     - [Day 3](#day-3)
 - [Scope](#scope)
 - [Trust model](#trust-model)
     - [Target execution](#target-execution)
     - [User Interface](#user-interface)
 - [Issues](#issues)
     - [[CommitteeTimelock] - Emits event even if the transaction was already queued](#committeetimelock---emits-event-even-if-the-transaction-was-already-queued)
     - [[CommitteeTimelock] - Can omit the events from the contract implementation](#committeetimelock---can-omit-the-events-from-the-contract-implementation)
     - [[CommitteeTimelock] - The computed txHash should not be considered unique for an execution](#committeetimelock---the-computed-txhash-should-not-be-considered-unique-for-an-execution)
     - [The voting period is shorter than 3 days](#the-voting-period-is-shorter-than-3-days)
     - [[CommitteeTimelock] - update require err message to reflect condition](#committeetimelock---update-require-err-message-to-reflect-condition)
 - [Artifacts](#artifacts)
     - [Sūrya](#surya)
     - [Coverage](#coverage)
     - [Tests](#tests)
 - [License](#license)


## Details

- **Client** Indexed Finance
- **Date** February 2021
- **Lead reviewer** Daniel Luca (@cleanunicorn)
- **Reviewers** Daniel Luca (@cleanunicorn), Andrei Simion (@andreiashu)
- **Repository**: [Sigma Comittee](https://github.com/indexed-finance/sigma-core)
- **Commit hash** `e3b2bed80e1c467b04d1d6121c06ddfc2e751fb6`
- **Technologies**
  - Solidity
  - Node.JS

## Issues Summary

| SEVERITY       |    OPEN    |    CLOSED    |
|----------------|:----------:|:------------:|
|  Informational  |  3  |  0  |
|  Minor  |  2  |  0  |
|  Medium  |  0  |  0  |
|  Major  |  0  |  0  |

## Executive summary

This report represents the results of the engagement with **Indexed Finance** to review **Sigma Comittee**.

The review was conducted over the course of **3 days** on **February 11, 2021**. A total of **5 person-days** were spent reviewing the code.

### Day 1

We started by going through the [initially provided document][Code changes summary] created by the client to have an initial idea about the recent changes.

We also set up a kickoff call with the client [which was recorded][kickoff call] to go through the general idea of the feature, the setup and the architecture of the system.

We continued to review the code, while creating an overview of the architecture to help us have a better understanding of the whole trust model.

### Day 2

We realised we don't have a complete understanding of the system and how the components are glued together, and we asked the client for an additional overview of the system, specifically how the the contracts will be deployed. We received an additional document detailing the [deployment and ownership strategy][Deplyment strategy].

We also asked for more time than initially estimated because we needed time to process all provided additional documentation.

### Day 3

During the final day of the review, we finalized clarifying any issues we identified, finalized the bulk of the report and set up a meeting with the client to deliver the report.

Recordings:
- [Kickoff call][Kickoff call] password: `C#w%d6CX`
- [Sync #1][Sync #1] password: `TKmx2?9r`

## Scope

Documentation: 
- [Code changes summary][Code changes summary]
- [Forum proposal][Forum proposal]
- [IIP 4: Sigma Pilot Snapshot Proposal][IIP4]
- [IIP 4: Sigma Pilot Thread][IIP4 Thread]
- [Deployment strategy][Deplyment strategy]

The initial review focused on the [Sigma Comittee](https://github.com/indexed-finance/sigma-core) identified by the commit hash `e3b2bed80e1c467b04d1d6121c06ddfc2e751fb6`.

We focused on manually reviewing the codebase, searching for security issues such as, but not limited to re-entrancy problems, transaction ordering, block timestamp dependency, exception handling, call stack depth limitation, integer overflow/underflow, self-destructible contracts, unsecured balance, use of origin, gas costly patterns, architectural problems, code readability.

**Includes:**
- The pull requests described in the document, specifically:
  - [PR #13](https://github.com/indexed-finance/sigma-core/pull/13)
  - [PR #15](https://github.com/indexed-finance/sigma-core/pull/15)
  - [PR #11](https://github.com/indexed-finance/sigma-core/pull/11)
  - [PR #7](https://github.com/indexed-finance/sigma-core/pull/7)
  - [PR #10](https://github.com/indexed-finance/sigma-core/pull/10)

[Code changes summary]: https://hackmd.io/WDQtAVf5Qwe5VfSw03VgAQ "Code changes summary"
[Forum proposal]: https://forum.indexed.finance/t/overview-of-changes-to-smart-contracts/171 "Forum proposal"
[Deplyment strategy]: https://hackmd.io/@d1ll0n/rkEklV4Wd
[Kickoff call]: https://us02web.zoom.us/rec/share/ViV5h5HDjYxWf67tb1wZ6jc6jnNlpGgYWehijbO5sryil6gS1ozus-T_P8d43lI.Jf10udDPfAcjQnoI
[Sync #1]: https://us02web.zoom.us/rec/share/8B34_UCeybBdgPW9qgn9Tj1O-bmES7mLDDgD4ihMuCiwABmKD1Ugt09iesLlc604.ql4AhVJk8dtO5hM6
[IIP4]: https://snapshot.page/#/ndx.eth/proposal/QmbneygJdeXFNzxrtVw7CTZAgLUwPBfxrCBzucefuWC1Q8 "IIP 4: Sigma Pilot"
[IIP4 Thread]: https://forum.indexed.finance/t/iip-4-sigma-pilot/74 "IIP 4: Sigma Pilot Thread"

## Trust model

We identified a few important parts of the system that hold increased trust and are critical to the system's correctness and well behavior.

### Target execution

Executing a transaction assumes the target will behave in a certain way. Even though Ethereum has an immutable contract system, there are ways to change how a contract behaves.

This can be done by:
Changing the contract's execution path by changing a storage slot, an external variable (like a timestamp) or a storage variable included in a separate contract
- Upgrading the contract's implementation to a different bytecode right before the target contract is executed

These are not all the ways the apparent contract execution can be unclear or misleading compared to the actual execution path and behavior.

Because the EVM offers an (almost) Turing-complete environment, it's virtually impossible to list all the ways the contract can trick an inexperienced observer into thinking it will not be malicious.

This, combined with the fact that some of the contracts can be upgradable and transaction reordering is a reality, can trick even the most experienced observer.

This is why there is a lot of trust the user has to put in the executed target and the actors who can upgrade parts of the system.

### User Interface

The voting process is another critical trustworthy part of the system that the users will put trust in. Even though they can verify on-chain that their votes will behave in a certain way, most of the users will not do that and will trust the web interface. This is because it's more complicated and tedious to do your own verifying. Thus, most of the users will trust the information relayed by the web interface.

The web interface inherently becomes a trust point between the system and the users.

The will also be other user interfaces the token holders will need to trust.

## Issues


### [[CommitteeTimelock] - Emits event even if the transaction was already queued](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/issues/6)
![Issue status: Open](https://img.shields.io/static/v1?label=Status&message=Open&color=5856D6&style=flat-square) ![Minor](https://img.shields.io/static/v1?label=Severity&message=Minor&color=FFCC00&style=flat-square)

**Description**

To run a transaction, it first needs to be queued by calling `queueTransaction`.


[code/contracts/committee/CommitteeTimelock.sol#L116-L122](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L116-L122)
```solidity
  function queueTransaction(
    address target,
    uint256 value,
    string memory signature,
    bytes memory data,
    uint256 eta
  ) public override isAdmin returns (bytes32) {
```


The arguments are encoded, and the resulting byte string is hashed as `txHash`.


[code/contracts/committee/CommitteeTimelock.sol#L128](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L128)
```solidity
    bytes32 txHash = keccak256(abi.encode(target, value, signature, data, eta));
```


The `txHash` is then marked as queued in a `queuedTransactions` mapping.


[code/contracts/committee/CommitteeTimelock.sol#L129](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L129)
```solidity
    queuedTransactions[txHash] = true;
```


When queuing transactions, the only check relates to the `eta` to ensure enough delay until the transaction can be executed.


[code/contracts/committee/CommitteeTimelock.sol#L123-L126](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L123-L126)
```solidity
    require(
      eta >= getBlockTimestamp().add(delay),
      "CommitteeTimelock::queueTransaction: Estimated execution block must satisfy delay."
    );
```


At the end of the `queueTransaction` method, an event is emitted with the provided parameters.


[code/contracts/committee/CommitteeTimelock.sol#L131](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L131)
```solidity
    emit QueueTransaction(txHash, target, value, signature, data, eta);
```


Even if the transaction was already queued, an event would be emitted. Thus, an admin could queue multiple times the same transaction but execute it only once. Each time the transaction is queued, an event is omitted. But only one `ExecuteTransaction` event will be emitted when the transaction is executed.


[code/contracts/committee/CommitteeTimelock.sol#L221](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L221)
```solidity
    emit ExecuteTransaction(txHash, target, value, signature, data, eta);
```


A web interface could become desynchronized if it reads multiple `QueueTransaction` events but only one matching `ExecuteTransaction` event.

**Recommendation**

Add a check in the method `queueTransaction` to ensure the transaction was not already queued before queueing the transaction.

```solidity
require(queuedTransactions[txHash] == false, "CommitteeTimelock::queueTransaction: Transaction already queued.")
```


---


### [[CommitteeTimelock] - Can omit the events from the contract implementation](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/issues/2)
![Issue status: Open](https://img.shields.io/static/v1?label=Status&message=Open&color=5856D6&style=flat-square) ![Minor](https://img.shields.io/static/v1?label=Severity&message=Minor&color=FFCC00&style=flat-square)

**Description**

The `CommitteeTimelock` is defined as an extension of the `ICommitteeTimelock` interface. The interface defines a set of events.


[code/contracts/interfaces/ICommitteeTimelock.sol#L5-L31](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/ed374bd8bbd948f78a4661182092c6c0a90baec9/code/contracts/interfaces/ICommitteeTimelock.sol#L5-L31)
```solidity
  event NewAdmin(address indexed newAdmin);
  event NewPendingAdmin(address indexed newPendingAdmin);
  event NewDelay(uint256 indexed newDelay);
  event CancelTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
  event ExecuteTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
  event QueueTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
```


And the `CommitteeTimelock` implementation redefines the same set of events.


[code/contracts/committee/CommitteeTimelock.sol#L21-L47](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/ed374bd8bbd948f78a4661182092c6c0a90baec9/code/contracts/committee/CommitteeTimelock.sol#L21-L47)
```solidity
  event NewAdmin(address indexed newAdmin);
  event NewPendingAdmin(address indexed newPendingAdmin);
  event NewDelay(uint256 indexed newDelay);
  event CancelTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
  event ExecuteTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
  event QueueTransaction(
    bytes32 indexed txHash,
    address indexed target,
    uint256 value,
    string signature,
    bytes data,
    uint256 eta
  );
```


This isn't necessary, and the event definition can be omitted in the implementation. This also protects from defining almost the same event with different arguments, or typos.

Solidity allows the definition and the emission of events that share the same name but have a different `topic` and arguments.

i.e.,

```solidity
interface IWithEvent {
    event TheEvent(uint n);
}

contract we is IWithEvent {
    event TheEvent(string n);
    
    function emitEvent() public {
        emit TheEvent(block.number);
        emit TheEvent("something else");
    }
}
```

`emitEvent()` will emit 2 very diffent events.

```json
[
    {
        "from": "0x358AA13c52544ECCEF6B0ADD0f801012ADAD5eE3",
        "topic": "0xd3d703951f7bff25f2e2896e97ba52c506eb73af2e72a1bd8bd2944e596609f8",
        "event": "TheEvent",
        "args": {
            "0": "7",
            "n": "7"
        }
    },
    {
        "from": "0x358AA13c52544ECCEF6B0ADD0f801012ADAD5eE3",
        "topic": "0x5286c814765d3cf19bf3c71af4bd8d4b1b3a7c6e748b608da0d23b4f83801ed4",
        "event": "TheEvent",
        "args": {
            "0": "something else",
            "n": "something else"
        }
    }
]
```

**Recommendation**

Remove the event definition from the `CommitteeTimelock` implementation which should leave you with the events defined in the interface `ICommitteeTimelock`.



---


### [[CommitteeTimelock] - The computed `txHash` should not be considered unique for an execution](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/issues/5)
![Issue status: Open](https://img.shields.io/static/v1?label=Status&message=Open&color=5856D6&style=flat-square) ![Informational](https://img.shields.io/static/v1?label=Severity&message=Informational&color=34C759&style=flat-square)

**Description**

In the `CommitteeTimelock` contract, an admin or a superUser can queue an execution by calling `queueTransaction`.


[code/contracts/committee/CommitteeTimelock.sol#L116-L122](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L116-L122)
```solidity
  function queueTransaction(
    address target,
    uint256 value,
    string memory signature,
    bytes memory data,
    uint256 eta
  ) public override isAdmin returns (bytes32) {
```


The arguments are packed together using `abi.encode`, and a `keccak256` is applied on top of the encoding.


[code/contracts/committee/CommitteeTimelock.sol#L128](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L128)
```solidity
    bytes32 txHash = keccak256(abi.encode(target, value, signature, data, eta));
```


The computed `txHash` is then saved in a mapping named `queuedTransactions`.


[code/contracts/committee/CommitteeTimelock.sol#L67](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L67)
```solidity
  mapping(bytes32 => bool) public override queuedTransactions;
```


The execution can be run by calling `executeTransaction` and specifying again all of the necessary arguments (previously used to compute `txHash`).


[code/contracts/committee/CommitteeTimelock.sol#L148-L154](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L148-L154)
```solidity
  function executeTransaction(
    address target,
    uint256 value,
    string memory signature,
    bytes memory data,
    uint256 eta
  ) public payable override isAdmin returns (bytes memory) {
```


If the queued execution passes all checks, it will be run, by internally calling `_executeTransaction`.

The internal method `_executeTransaction` checks if a function signature was provided, and if none exists, it assumes the `bytes memory data` already contains the function selector.


[code/contracts/committee/CommitteeTimelock.sol#L209-L213](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/blob/858ff477bdacb4a32e5b1f5e6bac122e25581992/code/contracts/committee/CommitteeTimelock.sol#L209-L213)
```solidity
    if (bytes(signature).length == 0) {
      callData = data;
    } else {
      callData = abi.encodePacked(bytes4(keccak256(bytes(signature))), data);
    }
```


This means that for the same execution, 2 different `txHashes` can exist, one with the `signature` specified, the other one with the signature contained in the `data` argument.

Not only 2 different `txHashes` can exist for the same execution (because the signature can be included in the `data` argument), but also ABI encoding makes it possible to decode multiple different byte arrays to the same arguments. This is possible because but not only:
- ABI encoding is not very strict
- Solidity accepts garbage data after all needed arguments were successfully parsed
- Address arguments are enclosed in 32 bytes, but only 20 bytes are significant, the first 12 bytes are erased when Solidity parses that argument; any bytes within the 12 bytes will change the hash, but not change the execution
- Strings have a length attached but enclosed in 32-byte blocks; any bytes after the specified length are ignored

**Recommendation**

It remains unclear

**[optional] References**


---


### [The voting period is shorter than 3 days](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/issues/4)
![Issue status: Open](https://img.shields.io/static/v1?label=Status&message=Open&color=5856D6&style=flat-square) ![Informational](https://img.shields.io/static/v1?label=Severity&message=Informational&color=34C759&style=flat-square)

**Description**

The newly elected Sigma Committee will have the ability to assign rewards for liquidity mining on new pools. To do this, any new distribution will have to go through a 7 day timelock - in theory, this gives NDX token holders 2 days to veto a token allocation: 

* Committee timelock has a 7 days execution delay
* GovernorAlpha has a 3 day voting period
* Indexed timelock has a 2 day execution delay

Compared to Indexed and Committee timelocks, which measure time in days, [GovernorAlpha.sol](https://github.com/indexed-finance/governance/blob/7473af351c9c38d12bb3741023b749442ef8d763/contracts/governance/GovernorAlpha.sol#L12-L13) measures time as the number of blocks mined since the start of a vote and assumes a block is mined every 15 seconds:

```solidity
  /// @dev The voting period which will be set after setVotingPeriodAfter has passed.
  uint256 public constant permanentVotingPeriod = 17_280; // ~3 days in blocks (assuming 15s blocks)
```

Currently, we have the following average block times:
* past 12 months: avg 13.11 seconds (range of minimum: 12.83 / maximum: 13.53 seconds)
* past 3 months: avg 13.08 seconds

Taking the past 3 months as a point of reference we get the following figures:

<img width="332" alt="Screenshot 2021-02-12 at 15 46 07" src="https://user-images.githubusercontent.com/342638/107747075-76511e80-6d49-11eb-8343-38afe1cb29c1.png">

This means that, in reality, NDX token holders currently have 2.6 days or just under 63 hours to pass a vote to veto a token allocation. This difference can confuse and potentially stop some users from acting in time to veto proposals if not properly communicated.

**Recommendation**

It might be worth ensuring that users understand that the voting period is less than 3 days so that they don't miss out on vetoing undesirable proposals.

Alternatively, expressing the time intervals as timestamps will ensure the time intervals are precise and predictable.



---


### [[CommitteeTimelock] - update `require` err message to reflect condition](https://github.com/monoceros-alpha/review-indexed-sigmacommittee-2021-02/issues/1)
![Issue status: Open](https://img.shields.io/static/v1?label=Status&message=Open&color=5856D6&style=flat-square) ![Informational](https://img.shields.io/static/v1?label=Severity&message=Informational&color=34C759&style=flat-square)

**Description**

The `require` error message does not mention `superUser` although it's one of the OR conditions in this modifier.


[code/contracts/committee/CommitteeTimelock.sol#L59-L65](https://github.com/monoceros-alpha/review-indexed-sigmacomittee-2021-02/blob/4c772f1edb078db49a4b441fe39e6efa6dc7f653/code/contracts/committee/CommitteeTimelock.sol#L59-L65)
```solidity
  modifier isAdmin {
    require(
      msg.sender == admin || msg.sender == superUser,
      "CommitteeTimelock::isAdmin: Call must come from admin."
    );
    _;
  }
```


**Recommendation**

Update the error message to: `Call must come from admin or superUser.`



---


## Artifacts

### Sūrya

Sūrya is a utility tool for smart contract systems. It provides a number of visual outputs and information about the structure of smart contracts. It also supports querying the function call graph in multiple ways to aid in the manual inspection and control flow analysis of contracts.

<!-- **Contracts Description Table**

```text
surya mdreport report.md Contract.sol
```

-->

#### Graphs

<!-- ***Contract***

```text
surya graph Contract.sol | dot -Tpng > ./static/Contract_graph.png
```

![Contract Graph](./static/Contract_graph.png)

```text
surya inheritance Contract.sol | dot -Tpng > ./static/Contract_inheritance.png
```

![Contract Inheritance](./static/Contract_inheritance.png)

```text
Use Solidity Visual Auditor
```

![Contract UML](./static/Contract_uml.png) -->

#### Describe

<!-- ```text
$ npx surya describe ./Contract.sol
``` -->

### Coverage

<!-- ```text
$ npm run coverage
``` -->

### Tests

<!-- ```text
$ npx buidler test
``` -->

## License

This report falls under the terms described in the included [LICENSE](./LICENSE).

<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/highlightjs-solidity@1.0.20/solidity.min.js"></script>
<script type="text/javascript">
    hljs.registerLanguage('solidity', window.hljsDefineSolidity);
    hljs.initHighlightingOnLoad();
</script><link rel="stylesheet" href="./style/print.css"/>
