# Installation, Access  & Development

Currently, there are four main ways to access the Bismuth programming language:

1. Via the [Nix](https://nixos.org/learn/) package manager (Recommended for users)
2. Via the development [Docker](https://www.docker.com/get-started/) image (Recommended for contributing to Bismuth)
3. Via building/installing manually from [source](https://github.com/bismuthlang/bismuth) (Recommended if neither of the above work)
4. Via the [online compiler](https://bismuth-lang.org/#editor) (Recommended for simple experiments)


## Via Nix

Using Nix to access Bismuth is currently the most versatile approach as it allows you to both
install Bismuth and also access a development environment for modifying Bismuth's source code.
The one limitation to using Nix is that Bismuth's test cases are validated using the Docker image.
Due to differences in the C/C++ compilers used for each approach, this means that running our test suite
via the Nix development shell may show some tests as failing when they would pass using the Docker image; however,
this does not impact actual use of Bismuth nor does it prevent contributing using the Nix provided development environment.

### Install Via Nix

Bismuth is currently packaged via a Nix Flake. As such, on a system with flakes enabled, all you need
to do to install Bismuth is to add the following to a NixOS/Home Manager's list of packages:
```nix
(builtins.getFlake "github:bismuthlang/bismuth").packages.${builtins.currentSystem}.default
```
The Bismuth compiler can then be accessed via running `bismuthc` in a shell.

### Access Via Nix

As a flake, Bismuth can also be accessed by running the following command in a shell:
```sh
nix build github:bismuthlang/bismuth
```
This will download and build the compiler into a newly created `./result/bin` directory. You can then cd into this directory
to use the executable or simply run `./result/bin/bismuthc`.

### Develop via Nix

After downloading the source code for Bismuth, running `nix develop` in the project's top level directory will
open a shell from which you will be able to compile the source code, run tests, etc.

## Via Docker

If you cannot access Nix, Docker provides a fairly reliable cross-platform solution to accessing and developing Bismuth.
The main downside to this approach is that you can't install Bismuth with it: instead, you have to access it via the
docker development shell.

### Access & Develop with Docker

Pre-requisites:
* Docker (CLI)
  * For Ubuntu, this can be done via running `sudo snap install docker`
* This repository downloaded locally (ie. `git clone https://github.com/bismuthlang/bismuth.git`)

After completing the pre-requisites, from a terminal, simply run the following command in the top level directory of project's repository:

```sh
source ./docker.sh
```
Running this command will place you into a shell for the Docker image which is setup to allow you to compile
Bismuth's source code and then run the produced executable.
The terminal will start in the working directory of /home/. The project files (the shared folder) is located at /home/shared.
For how to do this, see the subsequent section on how to develop/contribute to Bismuth.

**Note**: The first time you open the project in the docker image, you'll want to do is copy the antlr runtime into the project's files as shown below *(Note: this should only need to be done once. Afterwards, the files should stay updated across runs of the docker image)*.

```sh
cd /home
cp libantlr4-runtime.a shared/antlr/lib/
```
You can then `cd /home/shared` and proceed with the rest of the development steps.


## Via Source Code (Manually)

Manually setting up your computer's environment to compile Bismuth is not recommended.
The main challenge with such an approach is that various different C/C++ compilers are not easily
interchangeable (i.e., if you use one compiler for one component of a project, you tend to need to
use the same compiler for all other portions of the project). For Bismuth, this means that the LLVM IR dev
library, ANTLR library, and the Bismuth source code all need to be compiled with the same compiler.
The challenge, however, is that LLVM is typically pre-packaged and installed system-wide. As such, you'll need
to use the same compiler for Bismuth as whatever was used to pre-package LLVM. For systems using apt (Debian, Ubuntu, etc),
this means that you'll typically need to use Clang despite the OS defaulting your C and C++ compiler to
GCC (hence, the docker image and nix flake to help ensure no environment conflicts). If you do wish to proceed with
a manual setup, the Docker file and nix flake should be a great starting place for seeing what dependencies you'll
need and how to configure your environment.

Nonetheless, if you do chose to go this route, Bismuth is funamentally a CMake project, so you can either
follow the development steps directly or simply cut to the chase by running the following to build the project:
```sh
cmake -S . -B build
cmake --build build
```
And the following to install it:
```sh
cmake --install .
```


## Via the Online Compiler

An online compiler for Bismuth can be accessed at https://bismuth-lang.org/#editor. This compiler allows you to quick try out
writing Bismuth programs. You will, however, be limited in compute time/resources and what imports you have access to via this approach.
Hence, this serves more as a scratchpad for you to experiment with and isn't a replacement for installing/running Bismuth locally.


## Contributing/Development Guide

Having used one of the above approaches to gain access to Bismuth's source code, the following steps can be taken to
modify and conribute to it:

### Step 1: Build the code
Running `./makeBuild.sh` will build the codebase. In very rare circumstances (ie, a change to the docker image's libraries) you may have to delete previously built files (`rm -rf ./build`) prior to running `./makeBuild.sh`

### Step 2. Running tests

Running `./runTests.sh` will run all the test cases and print a report of the successes and failures.

### Step 5. Compiling a Bismuth program

Running `./tester.sh <.bismuth file without extension>` will compile the program and run it (if compiling was successful).

For example, to run `./programs/example.bismuth`, one could run the command `./tester.sh ./programs/example`.

To compile a program with the Bismuth standard library, use `./compileBSL.sh` instead of `./tester.sh`.

### Step 6. Generating code coverage
*Note: This process may take a while to run*

Running `./coverage.sh` will:
1. Delete the `./cov` folder
2. Build the code into the `./cov` folder
3. Run all tests *(Note: all tests must pass for coverage to generate!)*
4. Output html files displaying code coverage to `./cov/coverage` *(Note: you may have to run `sudo chown -R $USER ./cov` from a terminal on your host to be able to view the files in a browser)*

### Step 7. Open a PR or Install it!

You can install Bismuth from such a development environment by running:
```sh
cmake --install .
```
