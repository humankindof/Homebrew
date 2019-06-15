# Homebrew install with brewpack.
Homebrew install with brewpack packages.yml file.
Used for some commonly used brew and cask packages as well as web dev packages.

# install Homebrew:
>/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# install brewpack:
install manual: rouanw/brewpack

> brew install brewpack
or
> brew rouanw/brewpack/brewpack

# create packages.yml for brewpack
This creates your brewpack install list
> brewpack init

#install packages with brewpack
> brewpack install --repo humankindof/brew


# add Homebrew Shell Completion
manual: https://docs.brew.sh/Shell-Completion

add to ~/.bash_profile:
> nano ~/.bash_profile

copy/paste:

<pre>
HOMEBREW_PREFIX=$(brew --prefix)<br />
if type brew &>/dev/null; then<br />
  for COMPLETION in "$HOMEBREW_PREFIX"/etc/bash_completion.d/*<br />
  do<br />
    [[ -f $COMPLETION ]] && source "$COMPLETION"<br />
  done<br />
  if [[ -f ${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh ]];<br />
  then<br />
    source "${HOMEBREW_PREFIX}/etc/profile.d/bash_completion.sh"<br />
  fi<br />
fi<br />

. $(brew --prefix asdf)/asdf.sh
</pre>

Alternatively, this will add completions for asdf only:
> echo -e '\n. $(brew --prefix asdf)/asdf.sh' >> ~/.bash_profile
Add if homebrew completions step is not done:
> echo -e '\n. $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash' >> ~/.bash_profile
