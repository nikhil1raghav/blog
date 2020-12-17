+++
title="Bash"
author="Nikhil"
date="2020-10-31"
description="Notes on shell scripting"
+++

- `#!` is used in header to specify path of an interpreter. Kernel also scans for the single option to be passed to that interpreter.
- Max length of `#!` line varies from 63 to 1023 characters according to the system, so keep it less than 64.
- `$1` --> First argument
- `$0` --> Name of the script
- `$?` --> Exit code of last command.
- `!!` --> last command in place
- `$#` --> Number of arguments passed
- `touch project{1,2,3}` is equivalent to `touch project1 project2 project3`
- `touch code{a..d}.cpp` is equivalent to `touch codea.cpp codeb.cpp codec.cpp coded.cpp`


