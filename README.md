# Swiss DLT Block Explorer

<!-- project logo w/ quick links -->
<p align="center">
  <img src="https://github.com/etclabscore/jade-media-assets/blob/master/j-explorer/j-explorer(PNG)/128x128.png?raw=true" />
</p>
<center>
  <h3 align="center">Expedition</h3>

  <p align="center">
    A block explorer for the Ethereum Stack.
    <br />
    <a href="https://expedition.dev">View Demo</a>
    ·
    <a href="https://github.com/etclabscore/expedition/issues/new?assignees=&labels=&template=bug_report.md&title=">Report Bug</a>
    ·
    <a href="https://github.com/etclabscore/expedition/issues/new?assignees=&labels=&template=feature_request.md&title=">Request Feature</a>
  </p>
</center>

![expedition_gif](https://user-images.githubusercontent.com/364566/94349388-d17fb000-fff8-11ea-92ae-71c002474a65.gif)

<!-- table of contents -->
## Table of Contents
  - [About the Project](#about-the-project)
  - [Getting Started](#getting-started)
      - [Prerequisites](#prerequisites)
      - [Installation](#installation)
- [Usage](#usage)
  - [Run Service](#run-service)
  - [Start explorer](#start-the-explorer)
  - [Configurations](#configurations)
- [Resources](#resources)
- [Original Repository](#original-repository)

<!-- about the project -->
## About the Project
[Expedition](https://expedition.dev) is a minimal block explorer for Ethereum Stack and utilizes [Jade Service Runner](https://github.com/etclabscore/jade-service-runner) for managing background services (Multi-Geth), OpenRPC for underlying functionality, and Pristine. It does not use a database, and can be configured to point at any remote RPC node for any EVM-based network. The goal of Jade Explorer is to provide a resource for network information and block exploration.

Explorer Features:
- Display chain id
- Syncing status
- Runtime configuration for endpoints
- Search by Block, Transaction, Address
- Charts for hash, transaction count, gas used, uncles
- Preview latest blocks with pagination
- Multi-language support

<!-- getting started with the project -->
## Getting Started
### Prerequisites
- node `v10.15.3` or later
- npm `v6.4.1` or later

### Installation
Clone/ download the project, and install dependencies.
```bash
git clone https://github.com/pcaversaccio/block-explorer-swissdlt.git && cd block-explorer-swissdlt && npm install
```

<!-- example usage, screen shots, demos -->
## Usage
### Run Service
If you don't have a [service-runner](https://github.com/etclabscore/jade-service-runner) running, then you can use the one in the package.json via: (or see the configuration section below to provide your own ethereum RPC URL):
```bash
npm run service-runner
```
*Jade Service Runner will run at http://localhost:8002/.*

#### Core-Geth & Service Runner

By default, core-geth service will run ETC mainnet. Jade Service runner conveniently contains the service in the `/.services/` directory of project.

```bash
# ./services/
.
└── core-geth
    └── 1.11.2
        └── core-geth
            └── 1.11.2
                └── classic
                    ├── geth
                    │   ├── chaindata
                    │   ├── ethash
                    │   └── nodes
                    └── keystore
```

### Start the Explorer
```bash
npm start
```
*The explorer will run at http://localhost:3000/.*

### Configurations Awl

#### Set RPC via URL

`?rpcUrl=` Set custom rpc url.

Example: https://expedition.dev/?rpcUrl=https://swissdlt-dev.appswithlove.net/rpc/

#### Configure Default URLs via Environment Variables

Override the ETH URL:

*Windows (cmd.exe)*
```
set "REACT_APP_ETH_RPC_URL=https://swissdlt-dev.appswithlove.net/rpc/" && npm start
```

*Windows (Powershell)*
```
($env:REACT_APP_ETH_RPC_URL = "https://swissdlt-dev.appswithlove.net/rpc/") -and (npm start)
```

*Linux, macOS (Bash)*
```
REACT_APP_ETH_RPC_URL=https://swissdlt-dev.appswithlove.net/rpc/ npm start
```

**OR**

Override the service runner URL:

*Windows (cmd.exe)*
```
set "REACT_APP_SERVICE_RUNNER_URL=https://swissdlt-dev.appswithlove.net/rpc/" && npm start
```

*Windows (Powershell)*
```
($env:REACT_APP_SERVICE_RUNNER_URL = "https://swissdlt-dev.appswithlove.net/rpc/") -and (npm start)
```

*Linux, macOS (Bash)*
```
REACT_APP_SERVICE_RUNNER_URL=https://swissdlt-dev.appswithlove.net/rpc/ npm start
```

## Resources
- [Ethereum JSON RPC Specification](https://github.com/etclabscore/ethereum-json-rpc-specification)
- [Jade Service Runner](https://github.com/etclabscore/jade-service-runner)
- [OpenRPC](https://open-rpc.org)
- [Pristine](https://github.com/etclabscore/pristine)

## Original Repository
This repository has been forked from [here](https://github.com/xops/expedition).