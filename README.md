# ✨ So you want to sponsor a contest

This `README.md` contains a set of checklists for our contest collaboration.

Your contest will use two repos: 
- **a _contest_ repo** (this one), which is used for scoping your contest and for providing information to contestants (wardens)
- **a _findings_ repo**, where issues are submitted. (We'll set that one up later.) 

Ultimately, when we launch the contest, this contest repo will be made public and will contain the smart contracts to be reviewed and all the information needed for contest participants. The findings repo will be made public after the contest is over and your team has mitigated the identified issues.

Some of the checklists in this doc are for **C4 (🐺)** and some of them are for **you as the contest sponsor (⭐️)**.

---

# Contest setup

## 🐺 C4: Set up repos
- [ ] Create a new private repo named `YYYY-MM-sponsorname` using this repo as a template.
- [ ] Get GitHub handles from sponsor.
- [ ] Add sponsor to this private repo with 'maintain' level access.
- [ ] Send the sponsor contact the url for this repo to follow the instructions below and add contracts here. (Example message below)
- [ ] Delete this checklist and wait for sponsor to complete their checklist.

## ⭐️ Sponsor: Provide contest details

Under "SPONSORS ADD INFO HERE" heading below, include the following:

- [ ] Name of each contract and:
  - [ ] lines of code in each
  - [ ] external contracts called in each
  - [ ] libraries used in each
- [ ] Describe any novel or unique curve logic or mathematical models implemented in the contracts
- [ ] Does the token conform to the ERC-20 standard? In what specific ways does it differ?
- [ ] Describe anything else that adds any special logic that makes your approach unique
- [ ] Identify any areas of specific concern in reviewing the code
- [ ] Add all of the code to this repo that you want reviewed
- [ ] Create a PR to this repo with the above changes.

---

# ⭐️ Sponsor: Provide marketing details

- [ ] Your logo (URL or add file to this repo - SVG or other vector format preferred)
- [ ] Your primary Twitter handle
- [ ] Any other Twitter handles we can/should tag in (e.g. organizers' personal accounts, etc.)
- [ ] Your Discord URI
- [ ] Your website
- [ ] Optional: Do you have any quirks, recurring themes, iconic tweets, community "secret handshake" stuff we could work in? How do your people recognize each other, for example? 
- [ ] Optional: your logo in Discord emoji format

---

# Contest prep

## 🐺 C4: Contest prep
- [ ] Rename this repo to reflect contest date (if applicable)
- [ ] Rename contest H1 below
- [ ] Add link to report form in contest details below
- [ ] Update pot sizes
- [ ] Fill in start and end times in contest bullets below.
- [ ] Move any relevant information in "contest scope information" above to the bottom of this readme.
- [ ] Add matching info to the [code423n4.com public contest data here](https://github.com/code-423n4/code423n4.com/blob/main/_data/contests/contests.csv))
- [ ] Delete this checklist.

## ⭐️ Sponsor: Contest prep
- [ ] Make sure your code is thoroughly commented using the [NatSpec format](https://docs.soliditylang.org/en/v0.5.10/natspec-format.html#natspec-format).
- [ ] Modify the bottom of this `README.md` file to describe how your code is supposed to work with links to any relevent documentation and any other criteria/details that the C4 Wardens should keep in mind when reviewing. ([Here's a well-constructed example.](https://github.com/code-423n4/2021-06-gro/blob/main/README.md))
- [ ] Please have final versions of contracts and documentation added/updated in this repo **no less than 8 hours prior to contest start time.**
- [ ] Ensure that you have access to the _findings_ repo where issues will be submitted.
- [ ] Promote the contest on Twitter (optional: tag in relevant protocols, etc.)
- [ ] Share it with your own communities (blog, Discord, Telegram, email newsletters, etc.)
- [ ] Optional: pre-record a high-level overview of your protocol (not just specific smart contract functions). This saves wardens a lot of time wading through documentation.
- [ ] Designate someone (or a team of people) to monitor DMs & questions in the C4 Discord (**#questions** channel) daily (Note: please *don't* discuss issues submitted by wardens in an open channel, as this could give hints to other wardens.)
- [ ] Delete this checklist and all text above the line below when you're ready.

---

# bveCVX by BadgerDAO contest details
- $30,000 USDC (plus $30,000 in tokens) main award pot
- Join [C4 Discord](https://discord.gg/EY5dvm3evD) to register
- Submit findings [using the C4 form](https://code423n4.com/2021-09-bvecvx-contest/submit)
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts September 2, 2021 00:00 UTC
- Ends September 8, 2021  23:59 UTC

This repo will be made public before the start of the contest. (C4 delete this line when made public)

[ ⭐️ SPONSORS ADD INFO HERE ]

## Have any question?
Message Alex on Discord: Alex The Entreprenerd#5686

## Preamble
The contracts below are part of Badger's SETT system, which is a fork of Yearn V1.

If you are not familiar with Yearn V1, see a note on the architecture after the list of contracts


## Intro
The goal of the audit is to find and mitigate security risks for our newest veCVXStrategy.

This strategy uses a token from another of our vault, the CVX Helper Vault (bCVX)
The veCVX Strategy will receive bCVX via the vault.earn call and it will then redeem the underlying CVX and then lock it in the new Convex Locker Contract.

Due to this interaction, the contracts below are in scope.

Half of the contracts are audited (the ones under Core Contracts) and provide the basic functionality and connection between the other contracts.

The other half of the contract is not audited with veCVXStrategy not even being live currently.

For the sake of completeness we also added `CvxLocker` and `CvxStakingProxy` which are contracts written by Convex.finance

## Smart Contracts

| Contract                 | Link                                                                                              |
|--------------------------|---------------------------------------------------------------------------------------------------|
| veCVXStrategy.sol        | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/contracts/veCVXStrategy.sol          |
| CvxLocker.sol            | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/contracts/locker/CvxLocker.sol       |
| CvxStakingProxy.sol      | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/contracts/locker/CvxStakingProxy.sol |
| StrategyCvxCrvHelper.sol | https://github.com/code-423n4/2021-09-bvecvx/tree/main/bCVX/StrategyCvxCrvHelper.sol              |
| BaseStrategy.sol         | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/deps/BaseStrategy.sol                |
| SettV3.sol               | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/contracts/deps/SettV3.sol            |
| Controller.sol           | https://github.com/code-423n4/2021-09-bvecvx/tree/main/veCVX/contracts/deps/Controller.sol        |


## Flow of funds for veCVXStrategy
![Flow of funds for veCVXStrategy](https://github.com/code-423n4/2021-09-bvecvx/tree/main/.github/flow.png?raw=true)


## veCVXStrategy.sol - 510 LOC

This is the most important contract for the audit.

Fundamentally we receive bCVX (see below), we then withdraw from it (to have CVX) and then we lock the CVX in the new `CvxLocker` by Convex

The goal of this audit is to determine if this strategy is safe, if there are ways to lock funds, grief depositors or if there are exploits that would lead to loss of funds.


### External Calls
- CVX_VAULT -> the CVX Helper Vault (see below), also the want for the Strategy
- LOCKER -> Contract in whcih we lock funds, see: `CvxLocker.sol`
- SUSHI_ROUTER -> To Swap funds, see: `IUniswapRouterV2.sol`
- Controller -> The Controller that can tell the strategy when to _withdraw, _withdrawAll or _deposit
- Vault -> The Vault this strategy is attached to

## CvxLocker.sol - 985 LOC

This is the contract that will lock CVX for 17 weeks
While this is not a contract we wrote, our strategy interacts with this contract and as such we need to be aware of potential vulnerabilitie in it

### External Calls
- _tokenAddress -> The token, see `IERC20.sol`
- stakingProxy -> See `CvxStakingProxy.sol`

## CvxStakingProxy.sol - 182 LOC

This contract stakes the CVX from the CvxLocker as a way to gain staking yield.
While this is not a contract we wrote, our strategy interacts with this contract and as such we need to be aware of potential vulnerabilitie in it

### External Calls
- rewards -> The Rewards Locker from Convex, see `ICvxLocker.sol`

## StrategyCvxCrvHelper.sol - 614 LOC

This strategy is the underlying strategy of the `want` we deposit in the `veCVXStrategy`. 
This token will also sit idle in the instance of the `SettV3` contract we will use as vault for the `veCVXStrategy`.

As such, uncovering and mitigating exploits such as stealing funds are critical to this audit.

This strategy stakes CVX in their staking contract and harvests and auto-compounds the rewards into more CVX

## External Calls
- cvxCrvRewardsPool -> The pool for staking rewards by Convex

# Core Contracts

While these contracts have all been audited, it's a good idea you familiarize yourself with them as they are part of the system

## BaseStrategy.sol - 417 LOC

This provides some basic methods for all strategies and specifies the way in which they interact with the vault and controller

### External Calls
- want -> The `want` we want to deposit
- controller -> The Controller which handles funds
- vault -> The Vault which handles deposits and withdrawals


## SettV3.sol - 386 LOC

This is the contract for the Vault, which handles deposits and withdrawals
This contract has already been audited, but due to it's interactiong with bCVX and bveCVX it's important you understand how it works

### External Calls
- token -> The `want` we want to deposit
- controller -> The Controller which handles funds
- strategy -> The strategy we want audited, see `veCVXStrategy.sol`

## Controller.sol - 208 LOC

This is the contract for the Controller which connects vaults with strategies

This contract has already been audited, but due to it's interactiong with bCVX and bveCVX it's important you understand how it works

### External Calls
- token -> The `want` we want to deposit
- controller -> The Controller which handles funds
- strategy -> The strategy we want audited, see `veCVXStrategy.sol`


## A note on Sett's / Yearn V1's architecture

The V1 architecture has 3 contracts:
- Vault -> Used to handle deposits and withdrawals
- Strategies -> Used to use the assets and earn yield
- Controller -> A contract that connects each Vault with each respective Strategy

Loading funds into a strategy is done via `vault.earn` (also `controller.earn`)

At all times, funds should either be in the Vault (idle, not invested), or in the Strategy.

Funds in the Strategy could be idle, i.e. waiting to be invested or kept there to facilitate withdrawals, or they should be invested, earning interest.

Earning rewards, is done by calling a function called `harvest`.

