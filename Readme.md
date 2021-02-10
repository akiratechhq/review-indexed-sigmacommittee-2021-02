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
     - [Week 1](#week-1)
     - [Week 2](#week-2)
 - [Scope](#scope)
 - [Recommendations](#recommendations)
 - [Issues](#issues)
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
|  Informational  |  0  |  0  |
|  Minor  |  0  |  0  |
|  Medium  |  0  |  0  |
|  Major  |  0  |  0  |

## Executive summary

This report represents the results of the engagement with **Indexed Finance** to review **Sigma Comittee**.

The review was conducted over the course of **1 day** from **February 11, 2021**. A total of **2 person-days** were spent reviewing the code.

### Week 1

During the first week, we ...

### Week 2

The second week was ...

## Scope

[Code changes summary](https://hackmd.io/WDQtAVf5Qwe5VfSw03VgAQ)

The initial review focused on the [Sigma Comittee](https://github.com/indexed-finance/sigma-core) identified by the commit hash `e3b2bed80e1c467b04d1d6121c06ddfc2e751fb6`. ...

<!-- We focused on manually reviewing the codebase, searching for security issues such as, but not limited to re-entrancy problems, transaction ordering, block timestamp dependency, exception handling, call stack depth limitation, integer overflow/underflow, self-destructible contracts, unsecured balance, use of origin, gas costly patterns, architectural problems, code readability. -->

**Includes:**
- The pull requests described in the document, specifically:
  - [PR #13](https://github.com/indexed-finance/sigma-core/pull/13)
  - [PR #15](https://github.com/indexed-finance/sigma-core/pull/15)
  - [PR #11](https://github.com/indexed-finance/sigma-core/pull/11)
  - [PR #7](https://github.com/indexed-finance/sigma-core/pull/7)
  - [PR #10](https://github.com/indexed-finance/sigma-core/pull/10)

**Excludes:**
- BadContract.sol

## Recommendations

We identified a few possible general improvements that are not security issues during the review, which will bring value to the developers and the community reviewing and using the product.

## Issues


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
