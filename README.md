# Rare Earth Token (RET)

**Rare Earth Token (RET)** is an ERC-20 digital asset deployed on Ethereum Mainnet and inspired by the strategic importance of rare earth elements in modern industry and technology.

RET is a blockchain-native digital asset. It does **not** represent, track, redeem for, or provide ownership of physical rare earth elements or other commodities.

The project is built around:

* transparent smart-contract architecture,
* public on-chain verification,
* a finite maximum token supply,
* clearly disclosed administrative controls,
* simple and independently verifiable token mechanics.

**Verified contract:**
`0x9728da076538ff9781566b6040D8819fC5da3f37`

> This README is a project and technical information resource. It does not determine the legal classification of RET or the regulatory status of any future distribution, public offer, admission to trading, market activity or crypto-asset-related service.

---

## About Rare Earth Token

Rare Earth Token is an independent digital-asset project with a publicly identifiable founder.

Its connection to rare earth elements is **conceptual and thematic**. Rare earths provide the project with a strategic and technological context, while RET itself remains an independent blockchain-based digital asset.

RET does not use the price, market value, inventory or ownership of rare earth elements as a mechanism for determining or supporting the value of the token.

No quantity of RET corresponds to a kilogram, unit, basket or other quantity of rare earth materials.

Any physical assets or rare earth materials owned by the founder or by any other person are separate from RET and do not constitute collateral, backing or reserve assets for the token.

---

## Core Characteristics

RET does **not** provide:

* ownership rights in rare earth elements or other physical assets,
* redemption rights,
* rights to project or treasury assets,
* equity rights,
* dividend rights,
* profit-sharing rights,
* debt claims,
* contractual yield or interest,
* holder governance rights,
* a peg to a currency, commodity, basket or index,
* a value-stabilisation mechanism.

The deployed RET contract does not implement:

* post-deployment minting,
* staking,
* automatic rewards,
* rebasing,
* transfer taxes,
* price oracles,
* automatic token emissions,
* upgradeable proxy logic.

---

## Token Supply

RET was deployed with an **initial and maximum possible supply of 30,000,000 RET**.

The complete supply was created once during contract deployment.

No additional RET can be minted after deployment.

Total supply may decrease when RET is permanently removed through the contract's burn functionality.

### Deployment Allocation

| Allocation               | Amount at Deployment |
| ------------------------ | -------------------: |
| Founder Allocation       |        1,000,000 RET |
| Contract Treasury        |       29,000,000 RET |
| **Initial Total Supply** |   **30,000,000 RET** |

**Initial founder allocation address:**
`0x2A1C0Aa331158186c11bBB84CBC48B880431b8dD`

The founder allocation address identifies the destination used during the initial deployment allocation. It should not be interpreted as a guarantee of the current balance of that address.

Current balances should always be verified directly on-chain.

---

## Treasury

The RET contract address held **29,000,000 RET immediately after deployment**.

These tokens are referred to as the **contract treasury** for project-documentation purposes.

Treasury RET:

* are RET token units held by the contract,
* do not constitute cash or commodity reserves,
* do not back the market value of RET,
* do not create a redemption value,
* do not create a claim for holders against the treasury or founder.

Treasury distributions are controlled by the Ethereum address returned by the contract's `owner()` function and are executed through publicly visible on-chain transactions.

This README does not define a fixed future treasury distribution schedule.

---

## Smart Contract Functions

RET uses OpenZeppelin-based ERC-20, burnable, pausable and ownership functionality.

### Holder and ERC-20 Functions

#### `transfer()` / `transferFrom()`

Standard ERC-20 token transfers.

`transferFrom()` requires sufficient allowance from the token holder.

#### `approve()`

Allows a holder to authorise another address or application to operate RET up to a specified allowance.

#### `burn(uint256)`

Allows a holder to permanently destroy their own RET.

Burned RET is removed from total supply.

#### `burnFrom(address,uint256)`

Allows an approved spender to burn RET from another address only within the allowance granted by that address.

The contract owner has no special ability to burn RET directly from holder wallets without allowance.

---

## Administrative Functions

RET contains centralized administrative functionality controlled by the current `owner()` address.

### `distribute(address,uint256)`

Transfers RET from the contract treasury to a specified address.

The function cannot move RET while the token is paused.

### `pause()` / `unpause()`

Allows the owner to globally suspend or restore RET state updates.

While RET is paused:

* ordinary transfers are blocked,
* treasury distributions are blocked,
* token burning is blocked.

RET does not contain a per-address blacklist mechanism.

### `rescueTokens(IERC20,uint256,address)`

Intended to recover ERC-20 tokens sent to the contract by mistake.

The deployed code does not technically exclude RET itself, meaning the function can also move RET held by the contract.

It does not provide access to RET stored in independent holder wallets.

### `sweepETH(address)`

Allows the owner to transfer ETH held by the RET contract to a non-zero destination address.

ETH held by the contract does not constitute backing or a redemption reserve for RET.

### `transferOwnership(address)`

Transfers the administrative owner role to a new non-zero Ethereum address.

The transfer is immediate and does not require acceptance by the new address.

### `renounceOwnership()`

Irreversibly removes the contract owner by setting ownership to the zero address.

After execution, all functions restricted by `onlyOwner` become permanently unavailable.

This function exists as an extreme technical option and is not presented as a routine project operation or declared project milestone.

---

## Founder and Contract Ownership

The **founder identity** and the **contract owner address** are separate concepts.

The hard-coded founder address identifies the destination of the initial 1,000,000 RET allocation.

Administrative control, by contrast, follows the current Ethereum address returned by:

```solidity
owner()
```

The owner address may change through `transferOwnership()`.

Moving administrative ownership between wallet addresses controlled by the same founder — including migration to a hardware-controlled address — changes the technical owner address without, by itself, changing the founder identity or project stewardship.

The current owner address should always be verified directly on-chain.

---

## Administrative Control

The RET contract is **not fully decentralized**.

The current owner address can:

* distribute RET held by the treasury,
* pause and unpause RET,
* recover tokens held by the contract,
* withdraw ETH held by the contract,
* transfer ownership,
* renounce ownership.

The owner cannot use these permissions to:

* mint additional RET,
* create inflation,
* impose transfer taxes,
* rebase holder balances,
* blacklist individual wallets,
* directly seize RET from holder wallets through a special owner function.

Administrative actions are publicly observable through Ethereum.

---

## Market and Liquidity

RET contains no mechanism intended to determine, guarantee, defend or stabilise a market price.

If secondary-market trading becomes available, market prices may be influenced by factors including:

* supply,
* demand,
* available liquidity,
* market conditions,
* broader crypto-asset market activity.

The founder and project do not guarantee:

* a specific market price,
* a minimum value,
* market demand,
* continuous liquidity,
* the ability to sell RET,
* any relationship between the price of RET and rare earth elements,
* financial returns.

A liquidity pool or third-party trading interface, if available, does not guarantee continuous market access or sufficient liquidity.

This README intentionally does not specify a starting price, launch date, liquidity-pool size, trading pair or purchase route.

---

## Risk Considerations

RET involves technological, operational and market risks.

Examples include:

* partial or total loss of market value,
* limited or unavailable liquidity,
* substantial price volatility,
* smart-contract limitations,
* Ethereum network disruptions,
* changing gas costs,
* loss or compromise of private keys,
* compromise or loss of the administrative owner key,
* incorrect ownership transfer,
* third-party wallet or application failures,
* risks associated with token allowances,
* risks associated with treasury concentration,
* regulatory changes.

The RET contract is not upgradeable through an owner-controlled proxy mechanism. If a technical limitation or defect exists in the deployed logic, the owner cannot simply replace the contract logic in place.

---

## Technical Parameters

| Parameter                             | Details                                      |
| ------------------------------------- | -------------------------------------------- |
| **Network**                           | Ethereum Mainnet                             |
| **Standard**                          | ERC-20                                       |
| **Contract Name**                     | RareEarthToken                               |
| **Token Name**                        | Rare Earth Token                             |
| **Symbol**                            | RET                                          |
| **Decimals**                          | 18                                           |
| **Initial / Maximum Possible Supply** | 30,000,000 RET                               |
| **Post-Deployment Minting**           | Not available                                |
| **Contract Address**                  | `0x9728da076538ff9781566b6040D8819fC5da3f37` |
| **Compiler**                          | v0.8.30+commit.73712a01                      |
| **Optimization**                      | Disabled                                     |
| **License**                           | MIT                                          |
| **Source Verification**               | Verified — Exact Match on Etherscan          |
| **Upgrade Mechanism**                 | None in deployed RET contract                |

---

## Transparency and Verification

RET operates on the public Ethereum blockchain.

Users can independently verify:

* token balances,
* transfers,
* total supply,
* contract interactions,
* treasury movements,
* ownership changes,
* pause and unpause events,
* verified source code.

Current blockchain state should be verified on-chain rather than inferred solely from project documentation.

**Etherscan:**
https://etherscan.io/address/0x9728da076538ff9781566b6040D8819fC5da3f37

---

## Documentation

### Whitepaper

**Whitepaper v2.2.pdf**

Whitepaper v2.2 is the current public project and technical information document for RET.

It describes:

* token architecture,
* deployment structure,
* treasury,
* smart-contract functions,
* administrative controls,
* holder rights and limitations,
* market and liquidity considerations,
* principal project risks.

Whitepaper v2.2 is **not presented as a formal MiCA crypto-asset white paper**.

Previous project-document versions are retained as part of the project's transparency history.

---

## Regulatory Information

RET documentation describes the factual characteristics of the deployed token and project.

It does not constitute a self-issued legal ruling on the classification of RET under MiCA, MiFID II, Polish law, United States law or any other legal regime.

Any future:

* public distribution,
* public offer,
* admission to trading,
* market activity,
* marketing communication,
* exchange activity,
* custody arrangement,
* crypto-asset service,

must be assessed separately against the law applicable at the relevant time.

Publication of this README or the project Whitepaper does not replace any formal document, disclosure, notification, authorisation or procedure that may be legally required for future activity.

Nothing in this README constitutes personalised investment advice or a promise of financial return.

---

## Project Links

* **Website:** https://rareearthret.com
* **Etherscan:** https://etherscan.io/address/0x9728da076538ff9781566b6040D8819fC5da3f37
* **GitHub:** https://github.com/RareEarthToken-gif/ret-site
* **Email:** [contact@rareearthret.com](mailto:contact@rareearthret.com)

---

## Founder

**Szymon Turski**
Founder of Rare Earth Token (RET)

* **LinkedIn:** https://www.linkedin.com/in/szymon-turski-872638207/
* **X:** https://x.com/szymon_zab48565

---

## Core Principle

**Rare Earth Token is a blockchain-native ERC-20 digital asset inspired by the strategic importance of rare earth elements. RET provides no ownership of rare earths, no asset backing, no redemption claim and no mechanism intended to maintain a stable value by reference to an external asset or value.**

**Szymon Turski**  
Founder of Rare Earth Token (RET)

- **LinkedIn:** https://www.linkedin.com/in/szymon-turski-872638207/
- **X:** https://x.com/szymon_zab48565
