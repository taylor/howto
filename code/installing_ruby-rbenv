How I use the Simple Ruby Version Management: rbenv -- https://github.com/sstephenson/rbenv

Follow the [rbenv github](https://github.com/sstephenson/rbenv) instructions.

In my bash I have a flag to set loading rvm or rbenv (you need to keep rvm
totally out of the way for rbenv).  I do the following in the case statement
for loading rbenv:

```bash
    if [ -s "$HOME/.rbenv/bin/rbenv" ] ; then
      PATH=$HOME/.rbenv/bin:$PATH
      eval "$(rbenv init -)"
    else
      echo "rbenv does not seem to be installed!"
    fi
```

Use [ruby-build](https://github.com/sstephenson/ruby-build) to install ruby
versions as it provides rbenv install.

Install ruby-build with

    PREFIX=$HOME/sw/depot/ruby-build ./install.sh
    cd ~/sw/depot
    stow ruby-build

Install a ruby version by specifying the version and the rbenv versions path like so:

    rbenv install 1.9.3-p0 ~/.rbenv/versions/1.9.3-p0
    Downloading http://pyyaml.org/download/libyaml/yaml-0.1.4.tar.gz...
    Installing yaml-0.1.4...
    Installed yaml-0.1.4 to /Users/taylor/.rbenv/versions/1.9.3-p0
    Downloading http://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p0.tar.gz...
    Installing ruby-1.9.3-p0...
    Installed ruby-1.9.3-p0 to /Users/taylor/.rbenv/versions/1.9.3-p0     
