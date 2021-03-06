# Installation

## Any platform

You can install Psc-Package on any platform by downloading the binary for your platform from [the releases page](https://github.com/purescript/psc-package/releases) and copying it somewhere on your PATH.

## Linux/OSX

### npm

You might install <http://npmjs.com/package/psc-package-bin-simple> either globally or via project depencies.

## Windows

If you're a **Windows Chocolatey** user, then you can install `psc-package` from the [official repo](https://chocolatey.org/packages/psc-package):

```
$ choco install psc-package
```

## Travis

```yaml
language: c
dist: trusty
sudo: required

cache:
  directories:
  - .psc-package
  - output

env:
  - PATH=$HOME/purescript:$HOME/psc-package:$PATH

install:
  - TAG=v0.12.0
  - PSC_PACKAGE_TAG=v0.4.1
  - wget -O $HOME/purescript.tar.gz https://github.com/purescript/purescript/releases/download/$TAG/linux64.tar.gz
  - tar -xvf $HOME/purescript.tar.gz -C $HOME/
  - chmod a+x $HOME/purescript
  - wget -O $HOME/psc-package.tar.gz https://github.com/purescript/psc-package/releases/download/$PSC_PACKAGE_TAG/linux64.tar.gz
  - tar -xvf $HOME/psc-package.tar.gz -C $HOME/
  - chmod a+x $HOME/psc-package

script:
  - ./travis.sh
```

See <https://github.com/purescript/package-sets/blob/6f9f0b0eaea5e3718c860bc0cbaa651a554aad21/.travis.yml>
