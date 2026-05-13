# Mac Tools

## XCode

- Download a specific Xcode version: <https://xcodereleases.com/>
- Add the downloaded `Xcode.xip` to `/Applications` and double-click to expand.
- If you have multiple Xcode versions, rename them (e.g. `Xcode-12.0.app`, `Xcode-12.1.app`).

```bash
# Set default Xcode version
sudo xcode-select -switch /Applications/Xcode.app

# Check default Xcode version
/usr/bin/xcodebuild -version
```

## Homebrew

Reference: <https://brew.sh>

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Midnight Commander

```bash
brew install mc
```

## Glogg — Log explorer

<https://glogg.bonnefon.org/>

## diff-so-fancy

<https://github.com/so-fancy/diff-so-fancy>

## git-foresta

<https://github.com/takaaki-kasai/git-foresta>
