# C(++) W/ CMake and Google Test using GitHub actions Template

![Release](https://img.shields.io/github/v/release/TomVer99/C-CPP_CMake_GTest-GithubActions?label=Release&style=flat-square)

![Maintained](https://img.shields.io/maintenance/yes/2022?label=Maintained&style=flat-square)
![Issues](https://img.shields.io/github/issues-raw/TomVer99/C-CPP_CMake_GTest-GithubActions?label=Issues&style=flat-square)
[![Build](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2Fatrox%2Fsync-dotenv%2Fbadge&label=Build&style=flat-square)](https://actions-badge.atrox.dev/TomVer99/repoName/Build)
[![Test](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2Fatrox%2Fsync-dotenv%2Fbadge&label=Test&style=flat-square)](https://actions-badge.atrox.dev/TomVer99/C-CPP_CMake_GTest-GithubActions/Test)

![license](https://img.shields.io/github/license/TomVer99/C-CPP_CMake_GTest-GithubActions?color=blue&label=License&style=flat-square)

## Usage

### 1. Creating a new repository

Click on the `Use this template` button on the top right of the repository page, and create a new repository as usual.

### 2. Changing template files

#### 2.1. [README.md](README.md)

At the top of the `README.md` file a couple of 'badges' are shown. These are generated by [shields.io](https://shields.io/). You can change the badges to represent your project by changing the URL. For example, to change the Release badge, change the URL to:

```markdown
![Release](https://img.shields.io/github/v/release/yourUsername/yourRepoName?label=Release&style=flat-square)
```

If you do not feel like changing the badges, you can remove them. Or if you feel like using different badges you can generate new ones at [shields.io](https://shields.io/).

#### 2.2. [LICENSE](LICENSE)

The `LICENSE` file is the license of the project. You can change it to another license, or remove it if you do not want to use a license.

It is recommended to use a pre existing license, as it is difficult to write a license yourself.

#### 2.3. [CI.yml](./.github/workflows/CI.yml)

The `CI.yml` file is the GitHub actions workflow file. It contains the steps that are executed when you push to the repository. Though it should work for most simple projects, you might want to change it to your liking.

#### 2.4. [.gitignore](.gitignore)

The `.gitignore` file is used by git to ignore files that should not be tracked. The `.gitignore` provided should be sufficient for most simple projects.

#### 2.5. CMake

The CMake files provided are meant to be a starting point for your project.

##### 2.5.1. [Main CMake](CMakeLists.txt)

In this CMake file 3 variables are defined that should be edited on creation of a new project:

- `ProjectName` - The name of the project
- `ProjectRunName` - The name of the program executable that is generated (this is postfixed with `_Run`).
- `ProjectTestName` - The name of the test executable that is generated (this is postfixed with `_Test`).

##### 2.5.2. [Source CMake](src/CMakeLists.txt)

In this CMake file the source and header files are added to the project. You can add more source and header files to `Sources` and `Headers` respectively.

Note that files not included here will not be compiled or tested.

##### 2.5.3. [Test CMake](test/CMakeLists.txt)

In this CMake file the test source files are added to the project. You can add more test source files to `Sources`.

### 3. Requirements

- [CMake](https://cmake.org/) - The build system used.
  - Manual install of CMake may not be required in some cases such as when using Visual Studio Code.
- C/C++ Compiler of your choice.

### 4. Unit tests

This template uses [Google Test](https://github.com/google/googletest). There is a [sample unit test](test/gtest_validation_test.cpp) in the `test` folder.

### 5. Building

#### 5.1. Command line

To build the project, run the following commands in the project folder:

```bash
mkdir ./build/

cmake -B ./build/ -DCMAKE_BUILD_TYPE=Debug

cmake --build ./build/ --target CHANGE_ME --config Debug

# To run tests:
cd ./build/

ctest
```

The above mentioned commands will build the project in debug mode. To build in release mode, replace `Debug` with `Release`.

If you want to build an executable, add `_Run` or `_Test`. See the [CMake](#25-cmake) section for more information.

#### 5.2. Visual Studio Code

Specific tools needed: [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) (manages CMake install, CMake is not needed to be installed manually).

##### 5.2.1. Running program

To build and run the project in Visual Studio Code, set the build target on the status bar (default located directly right of the `Launch the selected target in the terminal window`). Then press the `Launch the selected target in the terminal window` button.

##### 5.2.2. Running tests

To build and run the tests in Visual Studio Code, press the `CTest` button in the status bar (default located to the right of the build target).
