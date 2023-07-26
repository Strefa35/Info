# Links:
    https://wiki.gnome.org/Apps

# Tools


## GNOME Tweaks
    https://itsfoss.com/gnome-tweak-tool/

    sudo add-apt-repository universe
    sudo apt install gnome-tweak-tool

    gnome-tweaks

## KeePass
    https://keepass.info/

    sudo apt-add-repository ppa:jtaylor/keepass
    sudo apt-get update
    sudo apt-get install keepass2

## Net Tools
    sudo apt install net-tools

## automake
    sudo apt install automake

## htop
    https://hisham.hm/htop/

    sudo apt install htop

## Putty
    https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
    https://websiteforstudents.com/installing-putty-on-ubuntu-16-04-17-10-18-04/

## GUI client to view git repositories
    https://wiki.gnome.org/Apps/Gitg/

    sudo apt install gitg

## Glogg - the fast, smart log explorer
    https://glogg.bonnefon.org/
    https://github.com/nickbnf/glogg

    sudo apt install glogg

## Klogg - Faster log explorer
    https://klogg.filimonov.dev/
    https://github.com/variar/klogg

## Visual diff and merge tools
    https://meldmerge.org/

    sudo apt install meld

## Visual Studio Code
    https://code.visualstudio.com/
    https://code.visualstudio.com/docs/setup/linux
    
    sudo code --user-data-dir=~/root

## Notepad++
    https://notepad-plus-plus.org/

    sudo snap install notepad-plus-plus

## Notepadqq
    https://itsfoss.com/notepadqq-notepad-for-linux/

    sudo add-apt-repository ppa:notepadqq-team/notepadqq
    sudo apt-get update
    sudo apt-get install notepadqq

## Kitty Terminal
    https://sw.kovidgoyal.net/kitty

    https://sw.kovidgoyal.net/kitty/binary.html#desktop-integration-on-linux

## Remmina
    https://remmina.org/

## diff-so-fancy
    https://github.com/so-fancy/diff-so-fancy

    mkdir ~/.local/diff-so-fancy

    cd ~/.local/
    git clone https://github.com/so-fancy/diff-so-fancy.git

    git config --global core.pager "diff-so-fancy | less --tabs=4 -RFX"
    git config --global interactive.diffFilter "diff-so-fancy --patch"

    ## modify .profile file 

    # set PATH to diff-so-fancy tool if it exists
    if [ -d "$HOME/.local/diff-so-fancy" ] ; then
        PATH="$HOME/.local/diff-so-fancy:$PATH"
    fi

    === as root ===
    cd /usr/local/bin
    git clone https://github.com/so-fancy/diff-so-fancy.git
    git config --global core.pager "diff-so-fancy | less --tabs=4 -RFX"
    vi /etc/environment
    add path to PATH="... :/usr/local/bin/diff-so-fency"

## Git scripts
    https://github.com/jwiegley/git-scripts

## git-forest
    https://github.com/takaaki-kasai/git-foresta

    git config --global core.pager "git-foresta --all --style=10 | less -RSX"

    git config --global core.pager "git-foresta --all --style=1 --graph-symbol-commit=★ --graph-symbol-tip=☆ --graph-margin-right=2 | less -RSX"

 ## modify .profile file 

  # set PATH to git-foresta tool if it exists
    if [ -d "$HOME/.local/git-foresta" ] ; then
      echo "GIT-FORESTA"
      PATH="$HOME/.local/git-foresta:$PATH"
    fi

## git-delta - A syntax-highlighting pager for git, diff, and grep output
	https://github.com/dandavison/delta

## Tig: text-mode interface for Git
    https://jonas.github.io/tig/

## Screen
    https://www.gnu.org/software/screen/

## tmux
    https://github.com/tmux/tmux/wiki

## Byobu
    https://www.byobu.org/

## Tmuxinator
    https://github.com/tmuxinator/tmuxinator	

## minicom
    https://help.ubuntu.com/community/Minicom
    http://manpages.ubuntu.com/manpages/trusty/man1/minicom.1.html

    sudo apt-get install minicom

    dmesg | grep tty

    sudo adduser $USER dialout

## Terminator
    https://github.com/gnome-terminator/terminator

## System analyzer

    systemd-analyze — Analyze and debug system manager


    https://elinux.org/Bootchart
    https://github.com/xrmx/bootchart

