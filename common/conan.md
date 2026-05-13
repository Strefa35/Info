# Conan — C/C++ Package Manager

## Install

```bash
pip install conan
pip install conan --upgrade
```

## Commands

Reference: <https://docs.conan.io/en/latest/reference/commands.html>

### Install requirements (conanfile.py / conanfile.txt)

```bash
conan install . --profile profiles/my-profile --install-folder=tmp/config
```

### Build a binary package

```bash
conan create . --source-folder=tmp/source --build-folder=tmp/build
```

### Call local `build()`

```bash
conan build . --source-folder=tmp/source --build-folder=tmp/build
```

## Remotes

Reference: <https://docs.conan.io/en/latest/uploading_packages/remotes.html>

```bash
conan remote add conan-center https://conan.bintray.com
conan remote add bincrafters https://api.bintray.com/conan/bincrafters/public-conan
conan remote add conan-community https://api.bintray.com/conan/conan-community/conan

conan remote list
```

## Developing Packages

Reference: <https://docs.conan.io/en/latest/developing_packages.html>

### Package development flow

<https://docs.conan.io/en/latest/developing_packages/package_dev_flow.html>

## conanfile.txt

<https://docs.conan.io/en/latest/reference/conanfile_txt.html>

## conanfile.py

<https://docs.conan.io/en/latest/reference/conanfile.html>

## Generators

<https://docs.conan.io/en/latest/reference/generators.html>
