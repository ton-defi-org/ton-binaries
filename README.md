# Pre-compiled TON binaries

Useful pre-compiled TON binaries (`fift`, `func`, `lite-client`) for multiple operating systems. These binaries are needed for various tasks related to TON blockchain, such as querying the chain, sending transactions and compiling smart contracts.

### Instructions

* Download the binaries from the [Releases](https://github.com/ton-defi-org/ton-binaries/releases) page of this repo - make sure to select the correct version according to the operating system you're using.

* After download, make sure the downloaded binaries are executable by changing their permissions (ie by running `chmod +x fift`). It's also useful to place these binaries in your path (or copy them to `/usr/local/bin`) to make sure you can access them from anywhere.

* To check that everything was installed correctly, run in terminal:
  ```
  fift -V && func -V && lite-client -V
  ```
  If everythibng works, you should see something like:
  ```
  Fift build information: [ Commit: 9875f02ef4ceba5b065d5e63c920f91aec73224e, Date: 2021-11-08 00:10:10 +0300]
  Func build information: [ Commit: 9875f02ef4ceba5b065d5e63c920f91aec73224e, Date: 2021-11-08 00:10:10 +0300]
  lite-client build information: [ Commit: 9875f02ef4ceba5b065d5e63c920f91aec73224e, Date: 2021-11-08 00:10:10 +0300]
  ```

## Alternative - compile by yourself

If you don't want to rely on pre-compiled binaries and prefer to compile the binaries by yourself, you can follow the [official instructions](https://ton.org/docs/#/compile). The gist of the instructions is provided below:

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
