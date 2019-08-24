# emacs configs

I like to play with other Emacs configs, but changing them and then back again
is a pain. This repo makes it super easy. Everyone else's cool emacs config is
just a submodule. Then, it can be symlinked to ~/.emacs.d and that symlink
changed as needed. My personalized configs are in my dotfiles repo.

## Installing

```zsh
git clone --recurse-submodules --depth=1 git@github.com:mattmc3/emacs-configs.git ~/.emacs-configs
ln -s ~/.emacs-configs/doom-emacs ~/.emacs.d
```

Remember that many of these configs require you to then install them after
they've been cloned, and they probably all pull from melpa. Read the directions
at their respective sites to understand what to do after symlinking.

### Installation note - Bug in Emacs <=26.2

Emacs has been experiencing a frustrating SSL bug, which presents when trying
to pull packages from MELPA. It's terrible, but switching from SSL seems to
be the currently accepted solution.

Example:

- Doom: `~/.emacs.d/bin/doom --insecure quickstart`
- Spacemacs: change ~/.spacemacs line `dotspacemacs-elpa-https t` to `dotspacemacs-elpa-https nil`

## Adding a submodule

```zsh
# Example to add spacemacs and track the develop branch
git submodule add -b develop https://github.com/syl20bnr/spacemacs.git spacemacs

# add doom-emacs
git submodule add -b straight https://github.com/hlissner/doom-emacs doom-emacs
```

## Updating submodules

```zsh
git submodule update --recursive --remote
```

## Cleaning the repo

```zsh
# remove all the untracked stuff
git clean -fd
```

## What's included

- [Doom Emacs][doom-emacs]
- [Spacemacs][spacemacs]


[doom-emacs]:  https://github.com/hlissner/doom-emacs
[spacemacs]:   https://github.com/syl20bnr/spacemacs
