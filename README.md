<p align="center">
    <h2 align="center">TreeCore Sim: A Lightweight cloudFPGA Prototype for Processor Simulation</h2>
</p>
<p align="center">
    <a href="https://github.com/microdynamics-cpu/tree-core-sim/actions">
      <img src="https://img.shields.io/github/workflow/status/microdynamics-cpu/tree-core-sim/unit-test/main?label=unit-test&logo=github&style=flat-square">
    </a>
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
$ mkdir dependency && cd dependency
```

Then, adding extra swap sapce to avoid the exhaustion of heap memory.
> NOTE: Below steps is not essential. If your embedded platform have more that 4GB memory space, you can just skip these steps.
```bash
$ mkdir -p ~/Desktop/swap
$ cd ~/Desktop/swap
$ sudo swapoff -a
$ sudo dd if=/dev/zero of=swapfile bs=1024 count=4000000 # 4GB swap file size
$ sudo mkswap swapfile
$ sudo swapon swapfile
```

> NOTE: The installation sequence of libraries is not arbitrary, some libraries have dependency relation. So you should install libraries one by one in order that's been exhibited here.
```bash
$ sudo apt-get install build-essential clang bison flex libreadline-dev gawk tcl-dev libffi-dev git mercurial graphviz xdot pkg-config python python3 libftdi-dev qt5-default python3-dev libboost-all-dev cmake libeigen3-dev
```

```bash
$ git clone https://github.com/YosysHQ/icestorm.git icestorm
$ cd icestorm
$ make -j$(nproc)
$ sudo make install
```
If your embedded platform is short of memory, you can decrease the number of jobs by switch `-j$(nproc)` into `-j1`.
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

> NOTE: After `nextpnr` compiled done, if you encouter  error in link phase like ` error: lto-wrapper failed collect2: error: ld returned 1 exit status`, that possible means the compiler of your embedded platform cannot support the [IPO](https://en.wikipedia.org/wiki/Interprocedural_optimization) perfactly. You need to switch `USE_IPO` option from `ON` to `OFF ` in [CMakefile.txt](./dependency/nextpnr/CMakefile.txt).

```bash
$ git clone https://github.com/YosysHQ/yosys.git yosys
$ cd yosys
$ make -j$(nproc)
$ sudo make install
```

## License
All of the TreeCore codes are release under the [GPL-3.0 License](LICENSE).

## Acknowledgement
1. [icesugar](https://github.com/wuxx/icesugar)

## Reference
