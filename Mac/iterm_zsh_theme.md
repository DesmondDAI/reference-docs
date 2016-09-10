# iTerm2 + zsh + Oh My Zsh + Solarized Dark theme

### Install iTerm2

[download -->](https://www.iterm2.com/)

[Install themes -->](http://iterm2colorschemes.com/)

<br>

### Install zsh

Use [homebrew](http://brew.sh/):
```shell
brew install zsh
```

Show all available shells:
```shell
cat /etc/shells
```

Change default shell to **zsh**:
```shell
chsh -s /bin/zsh
```

Reopen **iTerm** and check recent shell:
```shell
echo $SHELL
```

<br>

### Install Oh My Zsh

Via `curl`:
```shell
curl -L https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

<br>

### Change theme for zsh

Open `~/.zshrc` file, change following config to your favourite theme:
```shell
ZSH_THEME="agnoster"
```

<br>

### Install patched font

Since **zsh** adopts [powerline](https://github.com/powerline/powerline) plugin as status line
and prompts customization, pre-patched and adjusted fonts are required. Clone the repo:
```shell
git clone https://github.com/powerline/fonts.git
```

Then run `./install.sh` to install all **Powerline Fonts**.

FYI, the font I like: **Sauce Code Powerline**

<br>

### Remove "user@computer" prompt

`"user@computer"` occupies so much space in line. If you use **agnoster** theme, you
should find `prompt_context() {...}` in **agnoster.zsh-theme**:
```shell
# Context: user@hostname (who am I and where am I)
prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)$USER@%m"
  fi
}
```

Therefore we can set `DEFAULT_USER` so as to simply prompt. Add followings in `~/.zshrc`:
```shell
# Set default user
DEFAULT_USER="DesmondDAI"
```
Done. <br>
[Read more](https://github.com/robbyrussell/oh-my-zsh/issues/2033)

<br>

### References:

- [More external zsh themes](https://github.com/robbyrussell/oh-my-zsh/wiki/External-themes)
- [More about agnoster theme](https://gist.github.com/agnoster/3712874)
- [Powerline Fonts](https://github.com/powerline/fonts)
