# Yarn Package Manager

<https://yarnpkg.com>

## Usage

### Start a new project

```bash
yarn init
```

### Install all dependencies

```bash
yarn
yarn install
```

### Add a dependency

```bash
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]

yarn add [package] --dev    # dev dependency
yarn add [package] --peer   # peer dependency
```

### Upgrade a dependency

```bash
yarn up [package]
yarn up [package]@[version]
yarn up [package]@[tag]
```

### List installed packages

```bash
yarn list --pattern [package]
```

### Upgrade package (classic API)

```bash
yarn upgrade [package]
```
