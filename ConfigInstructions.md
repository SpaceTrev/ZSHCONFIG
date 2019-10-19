# Configuring Starship with ZSH shell

### 1. First download starship
`$ brew install starship`

### 2. Then configure zshell on your machine for mac after upgrading to catalina
`$ chsh -s /bin/zsh`

### Open in vs code on mac os
`$ code ~/.config/starship.toml`
##### for mac os

# enable the default zsh completions!
`$ code ~/.zshrc`
### populate ~/.zshrc with
autoload -Uz compinit && compinit

### Go back to ~/.zshrc and fill
zstyle ':completion:*:*:git:*' script ~/.zsh/git-completion.bash
fpath=(~/.zsh $fpath)
alias ..='cd ..'
alias ...='cd ../..'
alias ls='ls -GwF'
alias ll='ls -alh'
alias zshrc='code ~/.zshrc'
alias gitconfig='code ~/.gitconfig'
eval "$(starship init zsh)"

##### Must install starship first for the last line to work ^^ eval "$(starship init zsh)"

# For configuring auto git completion n sturfff and starship
### make the '.zsh' directory
`$ mkdir -p ~/.zsh`
`$ cd ~/.zsh`

### download the scripts for completion in that ~./zsh dir
`$ curl -o git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash`

`$ curl -o _git https://raw.githubusercontent.com/git/git/master/contrib/completion.zsh`


# Copy Paste the following in starship.toml or wherever it lives on your machine
prompt_order = [
    "username",
    "hostname",
    "kubernetes",
    "directory",
    "git_branch",
    "git_state",
    "git_status",
    "package",
    "dotnet",
    "golang",
    "java",
    "nodejs",
    "python",
    "ruby",
    "rust",
    "nix_shell",
    "conda",
    "memory_usage",
    "aws",
    "env_var",
    "cmd_duration",
    "line_break",
    "jobs",
    "battery",
    "time",
    "character",
]

[kubernetes]
symbol = "⛵ "
style = "dim green"
disabled = false

[git_state]
progress_divider = " of "
cherry_pick = "🍒 PICKING"
rebase = "⚾ REBASING"
disabled = true

[git_status]
conflicted = " ❌ "
ahead = " 🏎💨 "
behind = " 🌤️ "
diverged = " ↔ "
untracked = " 🤷‍ "
stashed = " 📦 "
modified = " 🍂 "
staged = " 🕺 "
renamed = " 👅 "
deleted = " 🗑 "

[character]
symbol = "🚀"

[directory]
fish_style_pwd_dir_length = 11
style = "fg:white bg:green"

[git_branch]
symbol = "🥦  "

[hostname]
ssh_only = false
prefix = "⟪"
suffix = "⟫"
trim_at = ".local"
disabled = false
style= "lightblue"

[jobs]
symbol = "+ "
threshold = 1
disabled = true

[time]
disabled = false
format = "⏰ [ %T ]"
utc_time_offset = -5
style = " li"

[python]
symbol = "🐍 "
pyenv_version_name = true
pyenv_prefix = "foo "
disabled = false

[cmd_duration]
min_time = 2 
prefix = "time "

[memory_usage]
show_percentage = true
show_swap = true
disabled = false
threshold = 0
symbol = "🐏 "
style = "bold purple"

[package]
symbol = "🥡 "

[[battery.display]]
threshold = 100
style = "bold"

[battery]
full_symbol = "🔋"
charging_symbol = "⚡️"
discharging_symbol = " 💀 "
