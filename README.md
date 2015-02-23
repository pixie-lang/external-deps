# external-deps

Sometimes it's useful to have pre-built versions of binaries for platforms that may have outdated/missing versions of libraries that Pixie needs. Currently this list includes only libuv, but will most likely grow over time. 


For libuv we need a version that's 1.0 or higher. Most platforms currently ship with version 0.10. 

To build the deps, use the following pattern: 

```
tar -xjf libuv.tar.bz2
mkdir ../externals
sh autoconf.sh
./configure --prefix=/path/to/../externals
make
make install
tar -cjf `uname -s`-`uname -m`.tar.bz2 ../externals/*
```
