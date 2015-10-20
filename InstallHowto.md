# Introduction #

Do NOT attempt to build from a checkout from the source code repository: that is for wizards only. Instead, grab one of the released source tarballs from the [downloads](http://code.google.com/p/schemafinder/downloads/list) tab.

This page will assist you in installing schemafinder from a source tarball.[[2](#2.md)]

# Prerequisites #

Prerequisites:
  1. gnu make
  1. working erlang installation.
    * debian: aptitude install erlang-dev
    * os/x (with [fink](http://www.finkproject.org/)): apt-get install erlang-otp
    * freebsd: pkg\_add -r erlang
    * others: ???
  1. [eunit](http://support.process-one.net/doc/display/CONTRIBS/EUnit) from process one
  1. [gencron](http://code.google.com/p/gencron)
  1. [combonodefinder](http://code.google.com/p/nodefinder)

Unpack the [tarball](http://code.google.com/p/schemafinder/downloads/list), then run configure and make check.
```
# tar -zxf schemafinder-2.0.1.tar.gz 
# cd schemafinder-2.0.1
# ./configure --prefix=/usr/local && make -s check
```
The default prefix is `/usr` so if you are ok with that then you can omit the prefix argument.  Hopefully you will see something like[[1](#1.md)]
```
...
PASS: copies-bug
==================
All 7 tests passed
==================
```
If not, the test output for test foo is in `tests/test-foo.out`; perhaps it is informative.

Now you can `make install` to stick stuff on your system.

# Footnotes #

## 1 ##
If you see something like:
```
fw requires GNU make to build, you are using bsd make
*** Error code 1

Stop.
```
Then you are using bsd make which will not work.  Try again with gnu make, e.g.,
```
# ./configure --prefix=/usr/local && gmake -s check
```

## 2 ##

Downloadable source tarballs use automake to build. A source code checkout of the repository uses [fwtemplates](http://code.google.com/p/framewerk) to build, and if you don't know what that is, you probably want to stick with the tarballs.