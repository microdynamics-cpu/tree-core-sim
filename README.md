<p align="center">
    <!-- <img width="200px" src="./.images/tree_core_logo.svg" align="center" alt="Tree Core CPU" /> -->
    <h2 align="center">TreeCore Sim: A Lightweight cloudFPGA Prototype for Processor Simulation</h2>
</p>
<p align="center">
    <a href="./LICENSE">
      <img src="https://img.shields.io/github/license/microdynamics-cpu/tree-core-sim?color=brightgreen&logo=github&style=flat-square">
    </a>
    <a href="https://github.com/microdynamics-cpu/tree-core-sim">
      <img alt="stars" src="https://img.shields.io/github/stars/microdynamics-cpu/tree-core-sim?color=blue&style=flat-square" />
    </a>
    <a href="https://github.com/microdynamics-cpu/tree-core-sim">
      <img src="https://img.shields.io/badge/total%20lines-0k-red?style=flat-square">
    </a>
    <a href="https://github.com/YosysHQ">
      <img src="https://img.shields.io/badge/toolchain-yosys%20nextpnr%20iceprog-red?style=flat-square">
  </a>
    <a href="./CONTRIBUTING.md">
      <img src="https://img.shields.io/badge/contribution-welcome-brightgreen?style=flat-square">
    </a>
</p>

## Overview
## Motivation
## Feature
## Usage

> NOTE: 
### Install
```bash
$ git clone https://github.com/microdynamics-cpu/tree-core-sim.git
$ cd tree-core-sim
```

```bash
$ mkdir -p ~/Desktop/swap
$ cd ~/Desktop/swap
$ sudo swapoff -a
$ sudo dd if=/dev/zero of=swapfile bs=1024 count=4000000 # 4GB swap file size
$ sudo mkswap swapfile
$ sudo swapon swapfile
```

```bash
$ sudo apt-get install build-essential clang bison flex libreadline-dev gawk tcl-dev libffi-dev git mercurial graphviz xdot pkg-config python python3 libftdi-dev qt5-default python3-dev libboost-all-dev cmake libeigen3-dev
```

```bash
$ git clone https://github.com/YosysHQ/icestorm.git icestorm
$ cd icestorm
$ make -j$(nproc)
$ sudo make install
```

```bash
$ git clone https://github.com/cseed/arachne-pnr.git arachne-pnr
$ cd arachne-pnr
$ make -j$(nproc)
$ sudo make install
```

```bash
$ git clone https://github.com/YosysHQ/nextpnr nextpnr
$ cd nextpnr
$ cmake -DARCH=ice40 -DCMAKE_INSTALL_PREFIX=/usr/local .
$ make -j$(nproc)
$ sudo make install
```

```bash
$ git clone https://github.com/YosysHQ/yosys.git yosys
$ cd yosys
$ make -j$(nproc)
$ sudo make install
```

## License
All of the TreeCore codes are release under the [GPL-3.0 License](LICENSE).

## Acknowledgement


## Reference
