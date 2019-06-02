# ***Warning; WIP!***
The software is still pre-alpha quality. Use at your own risks.

# igcc - yet another interactive shell for C development

<div align="center">
<img src=image/tty.gif "tty">
</div>

## Overview
igcc is an interactive shell for C development, 
which can be utilized like REPL (Read-Eval-Print-Loop)
 for dynamic languages such as Lisp.
It would be useful for testing new libraries or learning C language.
igcc is basically a thin wrapper around gcc, 
which invokes the compiler for each lines. 
Its features and limitations are listed below:

**Features**
- written in less than 700 lines of bash script
- line editting with GNU Readline
- some useful commands
- tab-completion of keywords and commands

**Limitations**
- do not support C preprocessor directives
- do not support function definition if use clang
- getting user input in C does not work correctly
- multiple lines are not allowed as input (use `:edit` instead)


## Requirements
- Bourne-again shell (bash) > 4.2
- GCC > 4.9 | Clang > 3.8

## Installation

Just put the script (igcc) into anywhere included in PATH.

## Usage
### Options

```
Usage: igcc [options]
Options:
  -h, --help                   show this help and exit.
  -v, --version                show version info and exit.
  -std <standard>              specify c dialect.
  -i, --interactive <boolean>  interactive or not. default: true when there is no "--eval" "--require", false in other cases
  -r, --require <file>         interpret file.
  -e, --eval <...>             evaluate script.
  --read-stdin <boolean>       whether to read from standard input. default: same as interactive
  -Pc <option>                 pass <option> to the c compiler.
  -cc <compiler>               specify c compiler.
  -x <language>                specify the language. permissible languages include: c. default: c
```

### commands

```
gnu11@(igcc)> :help
    :clear              clear history and reset environment.
    :edit               invoke /usr/bin/nano.
    :exit               exit igcc.
    :help               show this help.
    :include            show added header files.
    :include <header>   add header file.
    :lib                show added shared libraries.
    :lib <library>      add shared library to be linked.
    :load <file>        restore enviroment from <file>.
    :save <file>        save current environment into <file>.      
    :show               show history.
    ! <command>         excute shell command.
```

If `source-highlight` is available on your system, `:show` uses it to highlight history.
Also, if `indent` is available, it is used to format history.

## See also
- [CINT](http://www.hanno.jp/gotom/Cint.html) - a C/C++ interpreter which supports ANSI-C
- [Cling](https://root.cern.ch/cling) - a C++ interpreter built on the top of LLVM and Clang
- [PicoC](https://gitlab.com/zsaleeba/picoc) - a small C interpreter, comes with REPL
- [TCC](https://bellard.org/tcc/tcc-doc.html#SEC1) - an embedable C compiler

# License
Distributed under [GPLv3](LICENSE)

# Author
[TANI Kojiro](https://github.com/koji-kojiro)\<kojiro0531@gmail.com\>
[Zaoqi](https://github.com/zaoqi/)\<zaomir@outlook.com\>
