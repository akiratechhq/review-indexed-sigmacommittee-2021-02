<div id="splash">
    <div id="project">
          <span class="splash-title">
               Project
          </span>
          <br />
          <span id="project-value">
               Sigma Committee
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
 - [Scope](#scope)
 - [Recommendations](#recommendations)
 - [Issues](#issues)
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
- **Repository**: [Sigma Committee](https://github.com/indexed-finance/sigma-core)
- **Commit hash** `e3b2bed80e1c467b04d1d6121c06ddfc2e751fb6`
- **Technologies**
  - Solidity
  - Node.JS

## Issues Summary

| SEVERITY       |    OPEN    |    CLOSED    |
|----------------|:----------:|:------------:|
|  Informational  |  1  |  0  |
|  Minor  |  0  |  0  |
|  Medium  |  0  |  0  |
|  Major  |  0  |  0  |

## Executive summary

This report represents the results of the engagement with **Indexed Finance** to review **Sigma Committee**.

The review was conducted over the course of **1 day** on **February 11, 2021**. A total of **2 person-days** were spent reviewing the code.

### Day 1

We started by going through the [initially provided document][Code changes summary] created by the client to have an initial idea about the recent changes.

We also set up a kickoff call with the client [which was recorded][kickoff call] to go through the general idea of the feature, the setup and the architecture of the system.

We continued to review the code, while creating an overview of the architecture to help us have a better understanding of the whole trust model.

### Day 2

The second week was ...

Recordings:
- [Kickoff call][Kickoff call] password: `C#w%d6CX`

## Scope

Documentation: 
- [Code changes summary][Code changes summary]
- [Forum proposal][Forum proposal]
- [IIP 4: Sigma Pilot Snapshot Proposal][IIP4]
- [IIP 4: Sigma Pilot Thread][IIP4 Thread]

The initial review focused on the [Sigma Committee](https://github.com/indexed-finance/sigma-core) identified by the commit hash `e3b2bed80e1c467b04d1d6121c06ddfc2e751fb6`. ...

<!-- We focused on manually reviewing the codebase, searching for security issues such as, but not limited to re-entrancy problems, transaction ordering, block timestamp dependency, exception handling, call stack depth limitation, integer overflow/underflow, self-destructible contracts, unsecured balance, use of origin, gas costly patterns, architectural problems, code readability. -->

**Includes:**
- The pull requests described in the document, specifically:
  - [PR #13](https://github.com/indexed-finance/sigma-core/pull/13)
  - [PR #15](https://github.com/indexed-finance/sigma-core/pull/15)
  - [PR #11](https://github.com/indexed-finance/sigma-core/pull/11)
  - [PR #7](https://github.com/indexed-finance/sigma-core/pull/7)
  - [PR #10](https://github.com/indexed-finance/sigma-core/pull/10)

[Code changes summary]: https://hackmd.io/WDQtAVf5Qwe5VfSw03VgAQ "Code changes summary"
[Forum proposal]: https://forum.indexed.finance/t/overview-of-changes-to-smart-contracts/171 "Forum proposal"
[Kickoff call]: https://us02web.zoom.us/rec/share/ViV5h5HDjYxWf67tb1wZ6jc6jnNlpGgYWehijbO5sryil6gS1ozus-T_P8d43lI.Jf10udDPfAcjQnoI
[IIP4]: https://snapshot.page/#/ndx.eth/proposal/QmbneygJdeXFNzxrtVw7CTZAgLUwPBfxrCBzucefuWC1Q8 "IIP 4: Sigma Pilot"
[IIP4 Thread]: https://forum.indexed.finance/t/iip-4-sigma-pilot/74 "IIP 4: Sigma Pilot Thread"

## Recommendations

We identified a few possible general improvements that are not security issues during the review, which will bring value to the developers and the community reviewing and using the product.

## Issues


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
