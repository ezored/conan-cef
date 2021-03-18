[![conan](https://github.com/ezored/conan-cef/actions/workflows/conan.yml/badge.svg?branch=master)](https://github.com/ezored/conan-cef/actions/workflows/conan.yml)

## Conan package recipe for [*cef*](https://bitbucket.org/chromiumembedded/cef)

The Chromium Embedded Framework (CEF) is an open source framework for embedding a web browser engine which is based on the Chromium core

## Issues

If you wish to report an issue, please do so here:

[Github Issues](https://github.com/ezored/conan-cef/issues)

## For users

### Basic setup

```
conan install conan-cef/89.0.7+gb5952bd+chromium-89.0.4389.72@ezored/testing
```

### Project setup

If you handle multiple dependencies in your project is better to add a *conanfile.txt*

```
[requires]
conan-cef/89.0.7+gb5952bd+chromium-89.0.4389.72@ezored/testing

[generators]
cmake
```

Complete the installation of requirements for your project running:

```
mkdir build && cd build && conan install ..
```

Note: It is recommended that you run conan install from a build directory and not the root of the project directory.  This is because conan generates *conanbuildinfo* files specific to a single build configuration which by default comes from an autodetected default profile located in ~/.conan/profiles/default .  If you pass different build configuration options to conan install, it will generate different *conanbuildinfo* files.  Thus, they should not be added to the root of the project, nor committed to git.


## Build and package

The following command both runs all the steps of the conan file, and publishes the package to the local system cache.  This includes downloading dependencies from "build_requires" and "requires" , and then running the build() method.

```
conan create . ezored/testing
```

### Available options
| Option        | Default | Possible Values  |
| ------------- |:----------------- |:------------:|
| use_sandbox      | False |  [True, False] |
| debug_info_flag_vs      | -Z7 |  ['-Zi', '-Z7'] |


## Add remote

```
conan remote add ezored "https://ezored.jfrog.io/artifactory/api/conan/ezored"
```

## License

[MIT](LICENSE.md)
