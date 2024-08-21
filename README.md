# Pre-compiled TON binaries

Useful pre-compiled TON binaries (`fift`, `func`, `lite-client`) for multiple operating systems. These binaries are needed for various tasks related to TON blockchain, such as querying the chain, sending transactions and compiling smart contracts.

### Instructions

1. Download the binaries from the [Releases](https://github.com/ton-defi-org/ton-binaries/releases) page of this repo - make sure to select the correct version according to the operating system you're using and install the additional dependencies:
    | Operating System | fift | func | lite-client | Additional dependencies |
    |------------------|------|------|-------------|-------|
    | MacOS M1 | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-m1-0.3.0/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-m1-0.3.0/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-m1-0.3.0/lite-client) | `brew install openssl` |
    | MacOS Intel | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-intel/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-intel/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-intel/lite-client) | `brew install openssl`<br>`brew reinstall readline` |
    | Windows 64 | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/windows-64/fift.exe) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/windows-64/func.exe) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/windows-64/lite-client.exe) | Install [OpenSSL 1.1.1](https://slproweb.com/download/Win64OpenSSL_Light-1_1_1q.msi) |
    | Ubuntu 22 | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-22-0.4.0/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-22-0.4.0/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-22-0.4.0/lite-client) | `sudo apt install libssl-dev` |
    | Ubuntu 18 | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-18-0.3.0/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-18-0.3.0/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-18-0.3.0/lite-client) | `sudo apt install libssl-dev` |
    | Ubuntu 16 | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-16/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-16/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/ubuntu-16/lite-client) | `sudo apt install libssl-dev` |
    | Debian 10 (Out of date) | [fift](https://github.com/ton-defi-org/ton-binaries/releases/download/debian-10/fift) | [func](https://github.com/ton-defi-org/ton-binaries/releases/download/debian-10/func) | [lite-client](https://github.com/ton-defi-org/ton-binaries/releases/download/debian-10/lite-client) | `sudo apt install libssl-dev` |
2. After download, make sure the downloaded binaries are executable by changing their permissions (ie by running `chmod +x fift`). It's also useful to place these binaries in your path (or copy them to `/usr/local/bin`) to make sure you can access them from anywhere.

3. To check that everything was installed correctly, run in terminal `fift -V && func -V && lite-client -V`

4. If you plan to use `fift`, also download [fiftlib.zip](https://github.com/ton-defi-org/ton-binaries/releases/download/macos-m1-0.2.0/fiftlib.zip), open the zip in some directory on your machine (like `/usr/local/lib/fiftlib`) and set the environment variable `FIFTPATH` to point to this directory.

## Alternative - compile by yourself

If you don't want to rely on pre-compiled binaries and prefer to compile the binaries by yourself, you can follow the [official instructions](https://ton.org/docs/#/compile). The gist of the instructions is provided below:

### Linux (Ubuntu / Debian)

```
sudo apt update
sudo apt install git make cmake g++ libssl-dev zlib1g-dev wget
sudo apt install pkg-config liblz4-1 liblz4-dev  libsecp256k1-0 libsecp256k1-dev libsodium23 libsodium-dev
cd ~ && git clone https://github.com/ton-blockchain/ton.git
cd ~/ton && git submodule update --init
mkdir ~/ton/build && cd ~/ton/build && cmake .. -DCMAKE_BUILD_TYPE=Release && make -j 4
```
## Other sources for binaries

The core team provides automatic builds for several operating systems as [GitHub Actions](https://github.com/ton-blockchain/ton/actions).

Click on the link above, choose the workflow on the left relevant to your operating system, click on a recent green passing build and under "Artifacts" download `ton-binaries`.
