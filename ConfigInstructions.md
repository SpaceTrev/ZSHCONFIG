# Configuring Starship with ZSH shell

# H3 1. First download starship
`$ brew install starship`

# H3 2. Then configure zshell on your machine for mac after upgrading to catalina
`$ chsh -s /bin/zsh`

# H3 Open in vs code on mac os
`$ code ~/.config/starship.toml`
# H5 for mac os

# enable the default zsh completions!
`$ code ~/.zshrc`
# H3 populate ~/.zshrc with
autoload -Uz compinit && compinit

# H3 Go back to ~/.zshrc and fill
zstyle ':completion:*:*:git:*' script ~/.zsh/git-completion.bash
fpath=(~/.zsh $fpath)
alias ..='cd ..'
alias ...='cd ../..'
alias ls='ls -GwF'
alias ll='ls -alh'
alias zshrc='code ~/.zshrc'
alias gitconfig='code ~/.gitconfig'
eval "$(starship init zsh)"

# H5 Must install starship first for the last line to work ^^ eval "$(starship init zsh)"

# For configuring auto git completion n sturfff and starship
# H3 make the '.zsh' directory
`$ mkdir -p ~/.zsh`
`$ cd ~/.zsh`

# H3 download the scripts for completion in that ~./zsh dir
`$ curl -o git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash`
`$ curl -o _git https://raw.githubusercontent.com/git/git/master/contrib/completion.zsh`


# Copy Paste the following in starship.toml or wherever it lives on your machine
[character]
symbol = "🚀"

[directory]
fish_style_pwd_dir_length = 10

[git_branch]
symbol = "🕊️ ️ "

[package]
symbol = "🥡 "