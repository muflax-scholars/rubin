# Rubin

Simpler version of Gary Bernhardt's [Rubies](https://github.com/garybernhardt/rubies). Because this isn't hard.

*rubin* just makes it easy to set some environment variables. It has no stubs, no auto-switching, just a bunch of *export* statements you can *source*.

# Usage

Install Ruby versions with [ruby-build](https://github.com/sstephenson/ruby-build), or any other way you want. For example, let's install the latest version into "~/local/ruby/default":

```
mkdir -p ~/local/ruby/
cd ~/local/ruby/
ruby-build 2.2.2 default
```

(Actually, I recommend you do:)
```
RUBY_CONFIGURE_OPTS=--with-jemalloc ruby-build 2.2.2 default
```
(because we want a faster allocator. But anyway.)

Now we can use *rubin* to set our environment:

```
source <(rubin --ruby "default")
```

Done. Put that in your shell profile. Who needs rbenv?

Want a different gemset?

```
source <(rubin --gems ".project")
```

And now your gems come from (and go into) ".project". Yay.

# Details

Basically, just read the script. If it's not self-documenting, then it shouldn't be used.
