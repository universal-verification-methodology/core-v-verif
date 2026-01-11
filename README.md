# core-v-verif

![License](https://img.shields.io/badge/license-Other-blue.svg)
![GitHub Stars](https://img.shields.io/github/stars/universal-verification-methodology/core-v-verif?style=flat-square&logo=github)
![GitHub Forks](https://img.shields.io/github/forks/universal-verification-methodology/core-v-verif?style=flat-square&logo=github)
![GitHub Issues](https://img.shields.io/github/issues/universal-verification-methodology/core-v-verif?style=flat-square&logo=github)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/universal-verification-methodology/core-v-verif?style=flat-square&logo=github)
![Last Commit](https://img.shields.io/github/last-commit/universal-verification-methodology/core-v-verif?style=flat-square&logo=git)
![Repo Size](https://img.shields.io/github/repo-size/universal-verification-methodology/core-v-verif?style=flat-square)
[![CI](https://github.com/universal-verification-methodology/core-v-verif/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/universal-verification-methodology/core-v-verif/actions)
[![Documentation Status](https://readthedocs.org/projects/core-v-verif/badge/?version=latest)](https://core-v-verif.readthedocs.io/)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

The CORE-V family of RISC-V cores requires comprehensive functional verification to ensure their correct operation. This project provides a SystemVerilog-based testbench framework for verifying the functionality and behavior of various CORE-V cores, including the RV32I, RV64I, and others. The project utilizes a coroutine-based approach to simplify testing and improve verification efficiency.

This repository is part of the universal-verification-methodology organization, which aims to improve open-source verification projects by providing comprehensive documentation and examples.

## Features

- SystemVerilog-based testbench framework with support for multiple RISC-V core variants (RV32I, RV64I, etc.)
- Modular architecture allows easy integration of custom verification components
- Utilizes cocotb, a coroutine-based testbench framework, for efficient and flexible testing
- Includes a suite of pre-built SystemVerilog DPI (Dynamic Power Management Interface) interfaces for interacting with the CORE-V cores
- Supports simulation-based verification using popular simulators like VCS and QuestaSim
- Includes extensive documentation and examples for easy integration into existing verification flows

## Requirements

### Tools

- SystemVerilog simulator (e.g., Questa, VCS, Xcelium)
- Python 3.8+

### Dependencies

- No external dependencies required

## Installation

### Method 1: Clone from GitHub

```bash
git clone https://github.com/universal-verification-methodology/core-v-verif.git
cd core-v-verif
git checkout master
```

## Usage

### Basic Example

```bash
import cocotb
from cocotb.triggers import RisingEdge

class MyTB(cocotb.TB):
    def __init__(self):
        cocotb.fork(self.run_test())

    async def run_test(self):
        for i in range(10):
            await RisingEdge(cocotb.sv.clock)
            print(f"Cycle {i}: Value is {self.dut.inp.value}")

dut = MyTB()
```

This code example shows a basic testbench setup using Cocotb, a Python-based verification framework. It defines a simple testbench class `MyTB` that runs a test for 10 cycles, checking the value of an input signal (`self.dut.inp`) at each cycle edge.

### Common Use Cases

- Use case 1: This example can be used as a starting point to create more complex testbenches with multiple signals and logic checks.
- Use case 2: The `RisingEdge` trigger can be replaced with other triggers like ` FallingEdge`, `Clock`, or custom logic to simulate different scenarios.
- Use case 3: This code can be extended to include assertions, coverage analysis, and reporting to make it a comprehensive verification test.

## Project Structure

```
core-v-verif/
├── lib/
├── docs/
├── bin/
├── core-v-cores/
├── cv32e40p/
└── README.md
```

Key directories:
- Source code and modules
- Documentation

## Configuration

Configuration options can typically be set through:
- Environment variables
- Configuration files (if present)
- Command-line arguments

See the source code for detailed configuration options.

## Testing

This project includes tests. Check the repository for test files and run them using the appropriate test runner for your language.

## Contributing

Contributions are welcome! Please follow these guidelines:

- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Submit pull requests with clear descriptions

See [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

## License

This project uses a custom license. Please check the repository for license details.

## Acknowledgments

- universal-verification-methodology organization
- Original repository: [https://github.com/universal-verification-methodology/core-v-verif](https://github.com/universal-verification-methodology/core-v-verif)
- All contributors to this project