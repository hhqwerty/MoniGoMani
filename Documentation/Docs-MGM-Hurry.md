<p align="left">
    <a href="https://matrix.to/#/+moni-go-mani:matrix.org">
        <img src="https://img.shields.io/matrix/MoniGoMani-Testing:matrix.org?label=Matrix%20Community&logo=matrix" alt="Join MoniGoMani on Matrix">
    </a>  <a href="https://discord.gg/xFZ9bB6vEz">
        <img src="https://img.shields.io/discord/819237123009150977?label=Discord%20Server&logo=discord" alt="Join CryptoStonksShallRise on Discord">
    </a> <a href="https://github.com/Rikj000/MoniGoMani/releases">
        <img src="https://img.shields.io/github/downloads/Rikj000/MoniGoMani/total?label=Total%20Downloads&logo=github" alt="Total Releases Downloaded from GitHub">
    </a> <a href="https://github.com/Rikj000/MoniGoMani/releases/latest">
        <img src="https://img.shields.io/github/v/release/Rikj000/MoniGoMani?include_prereleases&label=Latest%20Release&logo=github" alt="Latest Official Release on GitHub">
    </a> <a href="https://github.com/Rikj000/MoniGoMani/blob/main/LICENSE">
        <img src="https://img.shields.io/github/license/Rikj000/MoniGoMani?label=License&logo=gnu" alt="GNU General Public License">
    </a> <a href="https://github.com/Rikj000/MoniGoMani/wiki">
        <img src="https://img.shields.io/badge/Docs-MoniGoMani-blue?logo=libreoffice&logoColor=white" alt="The current place where you can find all MoniGoMani Documentation!">
    </a> <a href="https://www.freqtrade.io/en/latest/">
        <img src="https://img.shields.io/badge/Trading%20Bot-Freqtrade-blue?logo=probot&logoColor=white" alt="Freqtrade - The open source crypto day-trading bot">
    </a> <a href="https://www.iconomi.com/register?ref=JdFzz">
        <img src="https://img.shields.io/badge/Join-ICONOMI-blue?logo=bitcoin&logoColor=white" alt="ICONOMI - The world’s largest crypto strategy provider">
    </a> <a href="https://www.buymeacoffee.com/Rikj000">
        <img src="https://img.shields.io/badge/-Buy%20me%20a%20Coffee!-FFDD00?logo=buy-me-a-coffee&logoColor=black" alt="Buy me a Coffee as a way to sponsor this project!">
    </a>
</p>


## ⚠️ Disclaimer
---

 - This Framework & Strategy are still experimental and under heavy development. It is not recommended running it live at this moment.
 - Always make sure to understand & test your MoniGoMani configuration until you trust it, before even thinking about going live!
 - I am in no way responsible for your live results! You are always responsible for your own MoniGoMani configuration!
 - MoniGoMani should always be [re-optimized](https://github.com/Rikj000/MoniGoMani/blob/main/Documentation/Docs-MoniGoMani.md#how-to-optimize-monigomani) after doing manual changes!
 - You need to [optimized](https://github.com/Rikj000/MoniGoMani/blob/main/Documentation/Docs-MoniGoMani.md#how-to-optimize-monigomani) your own copy of MoniGoMani while thinking logically, don't follow your computer blindly!
<hr>


<p align="center">
<img src="https://user-images.githubusercontent.com/86197446/123507408-6d624900-d669-11eb-9606-4a022bc4a117.png" width="300" height="289" align="center">
</p>

MGM-Hurry is a command line tool to speedup & simplify the setup & usage of [Freqtrade](https://www.freqtrade.io/en/stable/) in combination with the [MoniGoMani](https://github.com/Rikj000/MoniGoMani) FrameWork & Strategy.
Setting it all up requires some knowledge of the entire process, until you found MGM-Hurry! 💨


## Table of Contents
---

- [## ⚠️ Disclaimer](#-️-disclaimer)
- [## Table of Contents](#-table-of-contents)
- [## Installation instructions](#-installation-instructions)
- [## `mgm-hurry` Command Usage](#-mgm-hurry-command-usage)
  - [`mgm-hurry --help`](#mgm-hurry---help)
  - [`mgm-hurry up`](#mgm-hurry-up)
  - [`mgm-hurry install_freqtrade`](#mgm-hurry-install_freqtrade)
    - [Options](#options)
  - [`mgm-hurry install_mgm`](#mgm-hurry-install_mgm)
    - [Options](#options-1)
  - [`mgm-hurry setup`](#mgm-hurry-setup)
  - [`mgm-hurry cleanup`](#mgm-hurry-cleanup)
  - [`mgm-hurry download_static_pairlist`](#mgm-hurry-download_static_pairlist)
  - [`mgm-hurry download_candle_data`](#mgm-hurry-download_candle_data)
    - [Options](#options-2)
  - [`mgm-hurry hyperopt`](#mgm-hurry-hyperopt)
    - [Options](#options-3)
  - [`mgm-hurry backtest`](#mgm-hurry-backtest)
    - [Options](#options-4)
  - [`mgm-hurry hyperopt_show_results`](#mgm-hurry-hyperopt_show_results)
    - [Options](#options-5)
  - [`mgm-hurry hyperopt_show_epoch`](#mgm-hurry-hyperopt_show_epoch)
    - [Options](#options-6)
  - [`mgm-hurry start_trader`](#mgm-hurry-start_trader)
    - [Option](#option)
- [## Example timeranges](#-example-timeranges)
- [Developer Notes](#developer-notes)
- [### Virtual Environment](#-virtual-environment)
- [### Continuous Integration](#-continuous-integration)
- [### Module headers](#-module-headers)

## Installation instructions
---
- **ToDo:** *Move Installation instructions to `Docs-VeryQuickStart.md`*
- **Note:** *Assumes Python 3.8+, Pip & Git are already installed on your system!*
- **Note:** *Ubuntu users first will need to [switch their `sh` to `bash`](https://unix.stackexchange.com/a/442517)*

MoniGoMani provides an all-in-one setup tool. It will guide you through the entire installation procedure. Not only for MoniGoMani, but Freqtrade also. You want the entire package, right? You will be up & HyperOpting (or Dry/Live Running) in no time! 🤙

To run the `installer.sh`, just run the following command:
```powershell
/usr/bin/env sh <(curl -s "https://raw.githubusercontent.com/Rikj000/MoniGoMani/development/installer.sh")
```

After installation all you need to do to get started is run:

```powershell
cd ./freqtrade-mgm
python3 mgm-hurry up
```

## `mgm-hurry` Command Usage
---

⚠️ A [shell alias](https://github.com/Rikj000/MoniGoMani/blob/development/Documentation/Docs-VeryQuickStart.md#pro-tip) has been configured for these shorter example commands.
If you haven't done that optional step then you will need to prefix all your commands with `python3`!


### `mgm-hurry --help`
Displays information about the commands and their usage.
General usage format: `python3 mgm-hurry [command] [options]`


### `mgm-hurry up`
Quick start command, launches an interactive wizard which guides you through the entire process of:
- Installing & configuring Freqtrade
- Installing & configuring MoniGoMani
- Configuring exchange API
- Configuring Telegram bot API
- Generating a static pairlist
- Downloading historic candle data for HyperOpting & BackTesting
- Running required HyperOpt runs
- BackTesting your setup
- And finally start trading!


### `mgm-hurry install_freqtrade`
Individual command to install Freqtrade.
#### Options
- **`--target_dir`:** *(Optional)* Specify where you wish to install Freqtrade
  - ***Defaults to:** The current directory*
- **`--branch`:** *(Optional)* Specify the Freqtrade branch you wish to install
  - ***Defaults to:** The `develop` branch, can also be `stable` branch for less bleeding edge but generally more stable version*
- **`--commit`:** *(Optional)* Specify a specific Freqtrade commit you wish to utilize
  - ***Defaults to:** The recommended commit for MoniGoMani*


### `mgm-hurry install_mgm`
Individual command to install MoniGoMani.
#### Options
- **`--target_dir`:** *(Optional)* Specify where you wish to install MoniGoMani
  - ***Defaults to:** The current directory*
- **`--branch`:** *(Optional)* Specify the MoniGoMani branch you wish to install
  - ***Defaults to:** The `development` branch, can also be `main` branch for less bleeding edge but generally more stable version*
- **`--commit`:** *(Optional)* Specify a specific MoniGoMani commit you wish to utilize
  - ***Defaults to:** The latest MoniGoMani commit*


### `mgm-hurry setup`
Setup command, launches an interactive wizard which lets you configure Freqtrade & MoniGoMani.


### `mgm-hurry cleanup`
Cleans up HyperOpt Result `.json` files so you can easily start a fresh HyperOpt.


### `mgm-hurry download_static_pairlist`
Retrieve and apply a current **Binance-USDT-Top-Volume-StaticPairList.json** file *(Using [Binance-Retrieve-Top-Volume-StaticPairList.json](https://github.com/Rikj000/MoniGoMani/blob/main/user_data/mgm_tools/Binance-Retrieve-Top-Volume-StaticPairList.json))*.

The amount of pairs in these top volume lists can be altered by opening up `Binance-Retrieve-Top-Volume-StaticPairList.json` and changing the `number_assets` value near the bottom of the file to the amount of pairs you'd like in your list.
Further you can also change the `min_days_listed` to make sure that all downloaded pairs where available for the duration of your whole HyperOpt timerange.


### `mgm-hurry download_candle_data`
Downloads candle data for a given timerange.
#### Options
- **`--timerange`:** *(Optional)* Specify the timerange for which you want to download candle data
  - Needs to be of the format `--timerange=yyyymmdd-yyyymmdd` or `--timerange=down/side/up`
  - ***Defaults to:** The `timerange` defined in your `.hurry` file.*
- **`--timerange`:** *(Optional)* Specify the timerange for which you want to download candle data
  - ***Defaults to:** The `timerange` defined in your `.hurry` file*


### `mgm-hurry hyperopt`
[HyperOpt](https://www.freqtrade.io/en/latest/hyperopt/) *(HyperSpace Parameter Optimization, a form of machine learning)* magic that will make your life easier!
Runs HyperOpt process to find out the most positive settings.

#### Options
- **`--timerange`:** *(Optional)* Specify the timerange upon which you want to HyperOpt
  - Needs to be of the format `--timerange=yyyymmdd-yyyymmdd` or `--timerange=down/side/up`
  - ***Defaults to:** The `timerange` defined in your `.hurry` file.*
- **`--strategy`:** *(Optional)* Specify the Strategy which you want to HyperOpt
  - **Defaults to:** The `strategy` defined in the `hyperopt` section of your `.hurry` file.
- **`--loss`:** *(Optional)* Specify the [HyperOptLoss](https://github.com/Rikj000/MoniGoMani/blob/main/Documentation/Docs-HyperOptLoss-Functions.md) which you want to use during HyperOpting
  - **Defaults to:** The `loss` defined in the `hyperopt` section of your `.hurry` file.
- **`--spaces`:** *(Optional)* Specify the HyperOpt [spaces](https://www.freqtrade.io/en/latest/hyperopt/#running-hyperopt-with-smaller-search-space) which you want to use during HyperOpting
  - **Defaults to:** The `spaces` defined in the `hyperopt` section of your `.hurry` file.
- **`--enable_protections`:** *(Optional)* Specify if HyperOpt should use [Protections](https://www.freqtrade.io/en/latest/includes/protections/)
  - **Defaults to:** `True`. Provide `False` to disable protections
- **`--random_state`:** *(Optional)* Specify the random state that HyperOpt will use.
  - This is needed to be able to get [reproducible results](https://www.freqtrade.io/en/latest/hyperopt/#reproducible-results) when doing comparison tests
- **`--apply_best_results`:** *(Optional)* Automatically apply the latest epoch found in the "best" HyperOpt Results table after a HyperOpt in the form of a `.json` file that the strategy will automatically load & use if found.
  - For MoniGoMani this will be the `mgm-hyperopt-results.json` file found in the `user_data` folder.
  - For other strategies this will be a `<strategy-name>.json` file found in the `user_data/strategies` folder
  - **Defaults to:** `True`. Provide `False` to disable automatic creation of a HyperOpt Results `.json` file.
- **`--clean_start`:** *(Optional)* Perform [`mgm-hurry cleanup`](#mgm-hurry-cleanup) before starting HyperOpt.
- **`--do_backtest`:** *(bool, Optional)* Do a BackTest after the HyperOpt?
  - **Defaults to:** True.
- **`--output_file_name`:** *(Optional)* Custom filename for the `.log` file being created.
  - **Defaults to:** `HyperOptResults-<Current-DateTime>.log`
- **`--jobs`:** *(Optional)* Amount of parallel workers (CPU cores) to use
  - **Defaults to:** Automatic detection *(Amount used will depend on the amount of cores available on your system)*

### `mgm-hurry backtest`
Runs BackTest process to find out more about the results found by HyperOpt.
#### Options
- **`--timerange`:** *(Optional)* The target timerange for backtesting.
  - **Defaults to:** timerange in `.hurry`.
- **`--strategy`:** *(Optional)* Specify the Strategy which you want to BackTest
  - **Defaults to:** The `strategy` defined in the `hyperopt` section of your `.hurry` file.
- **`--enable_protections`:** *(Optional)* Whether or not to enable protections.
  - **Defaults to:** True.
- **`--output_file_name`:** *(Optional)* Custom name for the '.log' file being created.
  - **Defaults to:** Defaults to 'BackTestResults-<Current-DateTime>'

### `mgm-hurry hyperopt_show_results`
- **ToDo:** *Scrap with [issue 105](https://github.com/Rikj000/MoniGoMani/issues/105)*
Launches a prompt to easily choose a certain `.fthypt` file to print epochs from.
#### Options
- **`--only_best`:** *(Optional)* Show only best epochs.
  - **Defaults to:** `True`. Provide `False` to disable filter.
- **`--only_profitable`:** *(Optional)* Show only profitable epochs.
  - **Defaults to:** `False`. Provide `True` to enable filter.


### `mgm-hurry hyperopt_show_epoch`
- **ToDo:** *Re-write with [issue 105](https://github.com/Rikj000/MoniGoMani/issues/105)*
Prints & applies the HyperOpt Results for an epoch of choice.

#### Options
- **`--epoch`:** ***(Mandatory)*** Provide the epoch from which you wish to print the results.
- **`--apply`:** *(Optional)* Apply the printed HyperOpt Results
  - **Defaults to:** `True`. Provide `False` to only print the results
- **`--fthypt`:** *(Optional)* Launches a prompt to easily choose a certain `.fthypt` file
  - **Defaults to:** The last known `.fthypt` file. Provide `True` to launch a prompt to easily choose a specific. `.fthypt` file.


### `mgm-hurry start_trader`
Start the trader. Your ultimate goal!

#### Option
- **`--dry_run`:** *(Optional)* Run the trader in Dry-Run mode.
  - **Defaults to:** `True`. Provide `False` to run in Live-Run mode.


## Example timeranges
---
Here are some examples of timeranges for each different market type (bearish, bullish etc).

|Trend    |Timerange            |
|-------- |-------------------- |
|Downtrend| `20210509-20210524` |
|Uptrend  | `20210127-20210221` |
|Sidetrend| `20210518-20210610` |
|Final    | `20210425-20210610` |

## Developer Notes


### Virtual Environment
---

It's adviced to use an isolated environment for this project. (Probably each project)
Using `pipenv` makes this super easy.

```powershell
brew install pipenv
```

>Install pip packages from Pipfile in isolated environment

```powershell
pipenv install -d  # -d to install dev dependencies also
```

>Execute commands in the environment is as easy as `pipenv run <your command>`

### Continuous Integration
---

We use GitHub Actions online (and `pre-commit` local) to run CI procedures after each push and PR. It runs code styling checks and unit tests. To run these checks on your machine it is adviced to use `pre-commit`.


> Install `pre-commit` tool
Installing a git pre-commit hook as configured in `.pre-commit-config.yaml`

```powershell
brew install pre-commit
```
*Note; this example uses [Homebrew](https://brew.sh/) to install `pre-commit` but you are free to use your preferred package manager.*

> Install the pre-commit script.
```powershell
pipenv run pre-commit install
```

> Run pre-commit only on files in current changeset.
```powershell
pipenv run pre-commit run
```

> Run pre-commit on all files in the repo.
```powershell
pipenv run pre-commit run -a
```

### Module headers
---

To generate a module header (ascii art), you need to run the following command:

```powershell
$ python3
$ from art import tprint
$ tprint("Whatever you want")
```

Copy and paste the ASCII art output 🍻