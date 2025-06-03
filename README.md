# beautify-mac-terminal

Beautify your Mac Terminal

# Steps

## 1. Install iTerm2

- Download and install iTerm2 from [this download link](https://iterm2.com/downloads.html)
- Make sure `zsh` is the default terminal shell. Check the default terminal shell by typing `echo $0` in the terminal.
  - If it's not the default, install it with `brew install zsh` using Homebrew. Then change the default shell by typing `chsh -s $(which zsh)`.

## 2. Install color scheme

Can't do without a nice color theme.

- Go to [iterm2colorschemes.com](https://iterm2colorschemes.com) and pick a theme of your liking. I'm going for [Gruvbox Dark](https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/GruvboxDark.itermcolors).
- Install the theme by following the description on the main page.

## 3. Install Oh My Zsh!

Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

- Install oh-my-zsh by using curl: \
  `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

## 4. Install a Nerd Font

Nerd Fonts patches developer targeted fonts with a high number of glyphs (icons).

- Download the font of your liking on [NerdFont.com](https://www.nerdfonts.com/font-downloads). I'm using Hack.
- Install the fonts you just downloaded.
- Go to the preferences in iTerm2 and set the font to the font you just installed.

## 5. Install Powerlevel10k

- Clone the repository: \
  `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"`
- Open ~/.zshrc, find the line that sets `ZSH_THEME`, and change its value to `"powerlevel10k/powerlevel10k"`.
- Reload ~/.zshrc by typing `source ~/.zshrc`.
- Follow instructions.

## 6. Additional plug-ins

- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
  - Install with Homebrew: `brew install zsh-syntax-highlighting`
  - Copy and paste the following in iTerm2 to add it to the .zshrc file: \
    `echo "source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc`
  - Reload the terminal by typing `source ~/.zshrc`.
- [zsh-auto-suggestions](https://github.com/zsh-users/zsh-autosuggestions)

  - Copy and paste the following in iTerm2: \
    `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
  - Add the plugin to the list of plugins for Oh My Zsh to load (inside ~/.zshrc): \

  ```
  plugins=(
      # other plugins...
      zsh-autosuggestions
  )
  ```

- [Color LS](https://github.com/athityakumar/colorls)
  - Install the colorls ruby gem with `sudo gem install colorls` in iTerm2.
  - Enable tab completion for flags by entering following line to your shell configuration file (~/.bashrc or ~/.zshrc): \
    `source $(dirname $(gem which colorls))/tab_complete.sh`
  - Add alias in .zshrc to replace ls command: \
    `alias lc='colorls'`
