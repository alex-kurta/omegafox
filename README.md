<p align="center">
  <img src="https://forge.fsky.io/oneflux/omegafox/raw/branch/main/additions/browser/branding/omegafox/VisualElements_150.png">
</p>

<h1 align="center">Ωfox</h1>

<h3 align="center">General-use browser based on <a href="https://github.com/daijro/camoufox">Camoufox</a></h3>

## Features

- Reversions of Camoufox defaults for general-purpose use:
  - Re-enabled CSS animations
  - Removed cursor highlighter
  - Re-enabled stock Firefox features that do not make outside connections
  - Search engine usage allowed
  - etc.

- Security enhancements:
  - Improved process isolation
  - Weak ciphers and outdated TLS versions disabled by default
  - Hardened compilation configuration
  - Bundled with [hardened_malloc](https://github.com/GrapheneOS/hardened_malloc)
  - More to come

## Building

First, clone this repository with Git:

```bash
git clone --depth 1 https://forge.fsky.io/oneflux/omegafox
cd omegafox
```

Next, build the Ωfox source code with the following command:

```bash
make dir
```

After that, you have to bootstrap your system to be able to build Ωfox. You only have to do this one time. It is done by running the following command:

```bash
make bootstrap
```

Finally you can build and package Ωfox using the following command:

```bash
python3 multibuild.py --target linux --arch x86_64 arm64 i686
```

<details>
<summary>
CLI Parameters
</summary>

```bash
Options:
  -h, --help            show this help message and exit
  --target {linux} [{linux} ...]
                        Target platform to build (Linux only)
  --arch {x86_64,arm64,i686} [{x86_64,arm64,i686} ...]
                        Target architectures to build for each platform
  --bootstrap           Bootstrap the build system
  --clean               Clean the build directory before starting

Example:
$ python3 multibuild.py --target linux --arch x86_64 arm64
```

</details>

## Thanks

- [Camoufox](https://github.com/daijro/camoufox) - For inspiring this project
- [GrapheneOS](https://github.com/GrapheneOS) - Hardened memory allocator
