# brew
brew installs

# -----
#install Homebrew:
# > /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# -----
#install brewpack:
# > brew install brewpack
#or
# > brew rouanw/brewpack/brewpack

#create packages.yml for brewpack
# > brewpack init

#installation manual: https://github.com/rouanw/brewpack

# -----
#install packages with brewpack
# > brewpack install --repo humankindof/brew

# -----
#add completions definitions for asdf

#add to ~/.bash_profile:
# > nano ~/.bash_profile

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

#or, at terminal:
# > echo -e '\n. $(brew --prefix asdf)/asdf.sh' >> ~/.bash_profile
# > echo -e '\n. $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash' >> ~/.bash_profile

# -----
