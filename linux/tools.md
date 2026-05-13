# Linux Tools

Reference: <https://wiki.gnome.org/Apps>

## GNOME Tweaks

Reference: <https://itsfoss.com/gnome-tweak-tool/>

```bash
sudo add-apt-repository universe
sudo apt install gnome-tweak-tool
gnome-tweaks
```

## KeePass

<https://keepass.info/>

```bash
sudo apt-add-repository ppa:jtaylor/keepass
sudo apt-get update
sudo apt-get install keepass2
```

## Net Tools

```bash
sudo apt install net-tools
```

## automake

```bash
sudo apt install automake
```

## htop

<https://hisham.hm/htop/>

```bash
sudo apt install htop
```

## Putty

- <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>
- <https://websiteforstudents.com/installing-putty-on-ubuntu-16-04-17-10-18-04/>

## Gitg — GUI git client

<https://wiki.gnome.org/Apps/Gitg/>

```bash
sudo apt install gitg
```

## Glogg — fast, smart log explorer

- <https://glogg.bonnefon.org/>
- <https://github.com/nickbnf/glogg>

```bash
sudo apt install glogg
```

## Klogg — faster log explorer

- <https://klogg.filimonov.dev/>
- <https://github.com/variar/klogg>

## Meld — visual diff and merge

<https://meldmerge.org/>

```bash
sudo apt install meld
```

## Visual Studio Code

- <https://code.visualstudio.com/>
- <https://code.visualstudio.com/docs/setup/linux>

```bash
sudo code --user-data-dir=~/root
```

## Notepad++

<https://notepad-plus-plus.org/>

```bash
sudo snap install notepad-plus-plus
```

## Notepadqq

<https://itsfoss.com/notepadqq-notepad-for-linux/>

```bash
sudo add-apt-repository ppa:notepadqq-team/notepadqq
sudo apt-get update
sudo apt-get install notepadqq
```

## Kitty Terminal

- <https://sw.kovidgoyal.net/kitty>
- <https://sw.kovidgoyal.net/kitty/binary.html#desktop-integration-on-linux>

## Remmina

<https://remmina.org/>

## delta — syntax-highlighting pager for git/diff/grep

<https://github.com/dandavison/delta/>

### Install

Download the musl `.deb` from <https://github.com/dandavison/delta/releases>:

```bash
sudo apt install ./git-delta-musl_0.19.2_amd64.deb
```

### Configure `~/.gitconfig`

```ini
[core]
    pager = delta

[interactive]
    diffFilter = delta --color-only

[include]
    path = ~/.local/delta/themes.gitconfig

[delta]
    true-color = always
    navigate = true
    hyperlinks = true
    hyperlinks-file-link-format = "vscode://file/{path}:{line}"
    features = arctic-fox
    side-by-side = true

[merge]
    conflictstyle = zdiff3

[diff]
    colorMoved = default
```

## diff-so-fancy

<https://github.com/so-fancy/diff-so-fancy>

### Install (as user)

```bash
cd ~/.local/
git clone https://github.com/so-fancy/diff-so-fancy.git

git config --global core.pager "diff-so-fancy | less --tabs=4 -RFX"
git config --global interactive.diffFilter "diff-so-fancy --patch"
```

Add to `~/.profile`:

```bash
if [ -d "$HOME/.local/diff-so-fancy" ]; then
    PATH="$HOME/.local/diff-so-fancy:$PATH"
fi
```

### Install (as root)

```bash
cd /usr/local/bin
git clone https://github.com/so-fancy/diff-so-fancy.git
git config --global core.pager "diff-so-fancy | less --tabs=4 -RFX"
# Add /usr/local/bin/diff-so-fancy to PATH in /etc/environment
```

## Git scripts

<https://github.com/jwiegley/git-scripts>

## git-foresta

<https://github.com/takaaki-kasai/git-foresta>

```bash
git config --global core.pager "git-foresta --all --style=10 | less -RSX"

git config --global core.pager "git-foresta --all --style=1 \
  --graph-symbol-commit=★ --graph-symbol-tip=☆ \
  --graph-margin-right=2 | less -RSX"
```

Add to `~/.profile`:

```bash
if [ -d "$HOME/.local/git-foresta" ]; then
    PATH="$HOME/.local/git-foresta:$PATH"
fi
```

## Tig — text-mode interface for Git

<https://jonas.github.io/tig/>

## Screen

<https://www.gnu.org/software/screen/>

## tmux

<https://github.com/tmux/tmux/wiki>

## Byobu

<https://www.byobu.org/>

## Tmuxinator

<https://github.com/tmuxinator/tmuxinator>

## minicom — serial communication

- <https://help.ubuntu.com/community/Minicom>
- <http://manpages.ubuntu.com/manpages/trusty/man1/minicom.1.html>

```bash
sudo apt-get install minicom

dmesg | grep tty

sudo adduser $USER dialout
```

## Terminator

<https://github.com/gnome-terminator/terminator>

## System analyzer

```bash
systemd-analyze    # analyze and debug system manager
```

- [Bootchart](https://elinux.org/Bootchart)
- <https://github.com/xrmx/bootchart>
