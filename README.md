# Homebrew Install with Brewpack.
Homebrew install with brewpack packages.yml file.<br />
Used for some commonly used brew and cask packages as well as web dev packages.

## Installation

* Install Homebrew:
  >/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  

* Install Brewpack:
  Install manual: https:www.github.com/rouanw/brewpack
  > brew install brewpack
  
  or

  > brew rouanw/brewpack/brewpack

## Brewpacks
### Inherit premade Brewpacks

* Usable examples:
  > brewpack install --repo humankindof/Homebrew
  > brewpack install --repo rouanw/packages

### Create Your own packages.yml file
Create your own local packages.yml file. When you run this command, the currently installed packages will be added to the file for you.

  * Create packages.yml
    > brewpack init

## asdf Considerations
asdf is installed with the humankinfof/Homebrew/packages.yml package. To make it work, You have to add Homebrew Shell Completion for Bash.

* Add Homebrew Shell Completion
  * For zsh:
    * manual: https://docs.brew.sh/Shell-Completion
  * For bash:
    * open: ~/.bash_profile
      > nano ~/.bash_profile
    * add:
<pre>
HOMEBREW_PREFIX=$(brew --prefix)
if type brew &>/dev/null; then
  for COMPLETION in "$HOMEBREW_PREFIX"/etc/bash_completion.d/*
  do
    [[ -f $COMPLETION ]] && source "$COMPLETION"
  done
  if [[ -f ${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh ]];
  then
    source "${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh"
  fi
fi

. $(brew --prefix asdf)/asdf.sh
</pre>
