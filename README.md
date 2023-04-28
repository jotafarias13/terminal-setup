# Terminal Setup on Mac

# Overview

This is my terminal setup on Mac. This setup was **heavily** inspired on two Youtube videos, [one](https://www.youtube.com/watch?v=CF1tMjvHDRA) from [Josean Martinez](https://www.youtube.com/@joseanmartinez) and [one](https://www.youtube.com/watch?v=0MiGnwPdNGE) from [Engineering with Utsav](https://www.youtube.com/@EngineeringwithUtsav).

# Homebrew

First of all, we need to install **homebrew** in case you don't have it. To do so, just run in yout terminal the following [script](https://brew.sh/).

``` shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

It will ask you to run some commands at the end to add `brew` to your `PATH`. Run then and you're go to go.

# iTerm2

Now, we need to install **iTerm2** using homebrew. Since we want a GUI, we need to install using cask.

``` shell
brew install --cask iterm2
```

# Git

If, for some unknown crazy reason, you don't have `git` installed, do it using homebrew.

``` shell
brew install git
```

# Oh My Zsh

Next, let's install [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) which is a community-driven framework for managing your zsh configuration. [Zsh](https://www.zsh.org/) is a shell designed for interactive use. To install, run:

``` shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

# Font and Theme

We will use the [PowerLevel10k](https://github.com/romkatv/powerlevel10k) theme for our terminal.

``` shell
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

We need to set the theme in our `~/.zshrc` file by adding the following line.

``` shell
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Now you need to either restart iTerm2 or run `source ~/.zshrc` to load the theme. Next, PowerLevel10k configuration wizard opens up and you can setup any way you want. If you ever want to change those configurations edit `~/.p10k.zsh` or just run:

``` shell
p10k configure
```


As for the color scheme, you can find lots of them in the [iTerm2 Color Schemes](https://iterm2colorschemes.com/) website. There you can follow the instructions to download and install them. Basically, you need to to iTerm Preferences, Profiles, Colors, Colors Presets, Import and select the color scheme you downloaded. I use the Github Dark scheme.

You should also configure the font size that is right for you. Go to Preferences, Profiles, Text, Font and set the size. For me, size 20 is enough.

# Plugins

## Autosuggestion

[Zsh autogesstion](https://github.com/zsh-users/zsh-autosuggestions) is a plugin that, as the name says, give you suggestion on commands while you're typing. To install it run:

``` shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Then, add the plugin to your `~/.zshrc` file.

``` shell
plugins=( 
    # other plugins...
    zsh-autosuggestions
)
```


## Syntax Highlighting

[Zsh autogesstion](https://github.com/zsh-users/zsh-syntax-highlighting) is a plugin that, as the name says, give you syntax highlighting on commands while you're typing. To install it run:

``` shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Then, add the plugin to your `~/.zshrc` file.

``` shell
plugins=( 
    # other plugins...
	zsh-syntax-highlighting
)
```

## Web Search

Web search allows you to search stuff easily by using the `google` command. If you want to search about zsh, for example, just run `google zsh` and a browser window will popup with the results. To install, you just need to add the plugin to your `~/.zshrc` file.

``` shell
plugins=( 
    # other plugins...
	web-search
)
```

