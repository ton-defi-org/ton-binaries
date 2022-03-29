# Pre-compiled TON binaries

Useful pre-compiled TON binaries (`fift`, `func`, `lite-client`) for multiple operating systems.

Download the binaries from the [Releases](https://github.com/ton-defi-org/ton-binaries/releases) page of this repo.

Make sure the downloaded binaries are executable by changing their permissions (ie by running `chmod +x fift`).

## Compilation instructions

### Linux (Ubuntu / Debian)

```
sudo apt update
sudo apt install git make cmake g++ libssl-dev zlib1g-dev wget
cd ~ && git clone https://github.com/newton-blockchain/ton.git
cd ~/ton && git submodule update --init
mkdir ~/ton/build && cd ~/ton/build && cmake .. -DCMAKE_BUILD_TYPE=Release && make -j 4
```

## Other sources for binaries

The core team provides automatic builds for several operating systems as [GitHub Actions](https://github.com/newton-blockchain/ton/actions).

Click on the link above, choose the workflow on the left relevant to your operating system, click on a recent green passing build and under "Artifacts" download `ton-binaries`.
