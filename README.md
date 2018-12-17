# Circuit
This is a personal C++ wrapper of [ABC](https://people.eecs.berkeley.edu/~alanmi/abc/),
A System for Sequential Synthesis and Verification.
Currently, it could performs efficient bitwise-based logic simulation.

## Requirements
To compile [ABC](https://github.com/berkeley-abc/abc), you need:
- gcc
- make
- libreadline

To compile the `circuit` project, further need:
- libboost
- ctags

## Getting Started
### Build ABC
In Ubuntu, you can simpily run:
```
sudo chmod +x configure.sh
```
```
sh configure.sh
```
It will automatically clone `ABC` to `./abc/`,
compile it into a shared library,
and put the library file into the system path `/usr/lib/`.

### Build Circuit
To generate a executable program, just use:
```
make
```
And it will generate a program named `main`.

Use `./main -?` to get help.
- usage: ./main [options] ...
- options:
-   -f, --file      Circuit file (string [=data/blif/c432.blif])
-   -g, --genlib    Map libarary file (string [=data/genlib/mcnc.genlib])
-   -e, --error     Error rate (float [=0.05])
-   -n, --number    Frame number (int [=1024])
-   -?, --help      print this message

The benchmarks are saved in `BLIF` format in the folder `./data/blif/`.

The standard cell libraries are saved in `GENLIB` format in the foler `./data/blif/`.

You can change the error rate for approximate computing with the argument `-e`,
and set the simulation frame number with the argument `-n`.
