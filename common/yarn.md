# Yarn package manager
    https://yarnpkg.com

# Usage

## Starting a new project
  yarn init

## Installing all the dependencies
  yarn
  yarn install

## Adding a dependency
  yarn add [package]
  yarn add [package]@[version]
  yarn add [package]@[tag]

## Adding a dependency to different categories of dependencies
  yarn add [package] --dev  # dev dependencies
  yarn add [package] --peer # peer dependencies

## Upgrading a dependency
  yarn up [package]
  yarn up [package]@[version]
  yarn up [package]@[tag]


# Lists installed packages and Filter dependencies by pattern
  yarn list --pattern [package]

# Upgrade package
  yarn upgrade [package]

