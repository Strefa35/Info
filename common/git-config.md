# Git configuration

## Shows current configuration
    git config --list

## Shows current configuration with origin
    git config --list --show-origin

## Gets global configuration
    git config --global --list

## Sets user & email
    git config --global user.name "Arkadiusz Czerwinski"
    git config --global user.email A.Czerwinski@pistacje.net

    git config --local user.name "Arkadiusz Czerwinski"
    git config --local user.email A.Czerwinski@pistacje.net

## Pretty formats
    https://git-scm.com/docs/pretty-formats/2.1.3#_pretty_formats
    https://your-source.nl/nerd-afdeling/pretty-formats-git-logs

    git config --global alias.adog "log --all --decorate --oneline --graph"

    [alias]

    git config --global alias.adog "log --all --decorate --oneline --graph"

    git config --global alias.gr    = "log --graph --full-history --all --color --pretty=tformat:\"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%s%x20%x1b[33m(%an,%x20%ar)%x1b[0m\""
    git config --global alias.grb   = "log --graph --full-history --color --pretty=tformat:\"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%s%x20%x1b[33m(%an,%x20%ar)%x1b[0m\""
    git config --global alias.hist  = "log --graph --color --pretty=tformat:'%h %ad | %s%d [%an]' --date=short"

    git config --global alias.lg    = "log --graph --pretty=tformat:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative"

    git config --global alias.ll    = "log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat"
    git config --global alias.ll2   = "log --pretty=tformat:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat"

    git config --global alias.ld    = "log --graph --pretty=format:"%C(yellow)%h\\ %C(green)%ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short"

    git config --global alias.ls    = "log --pretty=format:"%C(green)%h\\ %C(yellow)[%ad]%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=relative"
    git config --global alias.ls2   = "log --pretty=tformat:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate"

