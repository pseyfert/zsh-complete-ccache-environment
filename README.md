# zsh complete ccache environment

This is somehow an extension for the [ccache
completion](https://github.com/pseyfert/zsh-complete-ccache-environment/blob/master/_export)
for zsh.

That completion can complete `ccache ⇥` and `export SOME_CCACHE_VARIABLE=⇥`,
but it cannot do `export CCACHE_⇥`. This is what I add in the completion
function here. It is a bit hacky (and at the time of writing not complete), but
you can give it a try. One part that made it especially hacky (and I should get
in contact with the zsh maintainers if we can do something better on the zsh
side) is that I want "tooltips" for the ccache variable names:

```sh
user@host somedir >> export CCACHE_⇥
ccache variables:
CCACHE_BASEDIR         -- relative to which top level paths are hashed
CCACHE_CC              -- specify compiler
CCACHE_COMPILERCHECK   -- compiler information included in the hash
CCACHE_COMPRESSLEVEL   -- cache compression level
CCACHE_DIR             -- where the cache and config are kept
CCACHE_EXTENSION       -- set extensions for intermediate files
CCACHE_EXTRAFILES      -- additional files to consider in hashing
CCACHE_IGNOREHEADERS   -- set paths to headers to ignore in hashing
CCACHE_LIMIT_MULTIPLE  -- cleanup level
CCACHE_LOGFILE         -- specify a log file
CCACHE_MAXFILES        -- maximum number of files in the cache
CCACHE_MAXSIZE         -- maximum size of the cache
CCACHE_NLEVELS         -- directory levels in the cache directory
CCACHE_PATH            -- path to the ccache directory
CCACHE_PREFIX          -- prefixes for compiler invokation
CCACHE_PREFIX_CPP      -- prefixes for preprocessor invokation
CCACHE_SLOPPINESS      -- hash files sloppy
CCACHE_TEMPDIR         -- where temporary files are kept
CCACHE_UMASK           -- set umask for ccache and child processes (e.g. for sharing cache)
```
