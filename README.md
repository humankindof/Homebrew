# Homebrew Install with Brewpack.
Homebrew install with brewpack packages.yml file.<br />
Used for some commonly used brew and cask packages as well as web dev packages.

* Install Homebrew:
  >/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  

* Install Brewpack:
  Install manual: https:www.github.com/rouanw/brewpack
  > brew install brewpack
  
  or

  > brew rouanw/brewpack/brewpack

* Create packages.yml for Brewpack
  This creates your brewpack install list<br />
It will import any already installed brew packages and casks on creation.
  * > brewpack init

# Brewpacks
## Install premade Brewpacks
* Usable examples:
> brewpack install --repo humankindof/Homebrew

> brewpack install --repo rouanw/packages

# asdf Considerations
asdf is installed with the humankinfof/Homebrew/packages.yml package. To make it work, You have to add Homebrew Shell Completion for Bash.

* Add Homebrew Shell Completion
  * For zsh see:
    * manual: https://docs.brew.sh/Shell-Completion
  * For bash:<br /><br />
    * open: ~/.bash_profile
    
      > nano ~/.bash_profile

add:
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

Alternatively, this will add completions for asdf only:
> echo -e '\n. $(brew --prefix asdf)/asdf.sh' >> ~/.bash_profile

Add if homebrew completions step is not done:
> echo -e '\n. $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash' >> ~/.bash_profile
