# lobotomy
A Brainf*ck interpreter written in C.

(Pardon my language.)

[![build status][build-status-badge-image]][build-status-url]
[![latest tag][latest-tag-badge-image]][latest-tag-url]
[![watchers][watchers-badge-image]][watchers-url]
[![stars][stars-badge-image]][stars-url]
[![issues][issues-badge-image]][issues-url]
[![forks][forks-badge-image]][forks-url]
[![contributors][contributors-badge-image]][contributors-url]
[![branches][branches-badge-image]][branches-url]
[![releases][releases-badge-image]][releases-url]
[![commits][commits-badge-image]][commits-url]
[![last commit][last-commit-badge-image]][last-commit-url]
[![license][license-badge-image]][license-url]

The brainf*ck language is a minimalistic imperative programming language, designed by Urban Müller around 1993.

From [the language's Wikipedia page](https://en.wikipedia.org/wiki/Brainfuck#Language_design):

The language consists of eight commands, listed below. A brainf*ck program is a sequence of these commands, possibly interspersed with other characters (which are ignored). The commands are executed sequentially, with some exceptions: an instruction pointer begins at the first command, and each command it points to is executed, after which it normally moves forward to the next command. The program terminates when the instruction pointer moves past the last command.

The brainf*ck language uses a simple machine model consisting of the program and instruction pointer, as well as a one-dimensional array of at least 30,000 byte cells initialized to zero; a movable data pointer (initialized to point to the leftmost byte of the array); and two streams of bytes for input and output (most often connected to a keyboard and a monitor respectively, and using the ASCII character encoding).

The eight language commands each consist of a single character:

| Character | Meaning |
|-----------|---------|
| > | Increment the data pointer (to point to the next cell to the right) |
| < | Decrement the data pointer (to point to the next cell to the left) |
| + | Increment (increase by one) the byte at the data pointer |
| - | Decrement (decrease by one) the byte at the data pointer |
| . | Output the byte at the data pointer |
| , | Accept one byte of input, storing its value in the byte at the data pointer |
| [ | If the byte at the data pointer is zero, then instead of moving the instruction pointer forward to the next command, jump it forward to the command after the matching ] command |
| ] | If the byte at the data pointer is nonzero, then instead of moving the instruction pointer forward to the next command, jump it back to the command after the matching [ command |

In a syntactically correct brainf*ck program, each [ character is matched uniquely by a ] character later in the program. This matching is similar to the way ( and ) characters match up into pairs in an algebraic expression.

An example of a "Hello, World!" program:

```
++++++++[>++++[>++>+++>+++>+<<<<-]>+>+>->>+[<]<-]>>.>
---.+++++++..+++.>>.<-.<.+++.------.--------.>>+.>++.
```

## Installation and Invocation (C)

(These instructions for the C implementation were tested on macOS)

First, ensure that gcc and make are installed.

After cloning this repo, cd into its directory and do this:

```sh
$ cd src/c
$ make
```

Then pass in the path of a brainf*ck program file as a command-line argument:

```sh
$ ./brainfsck ../../examples/hello-world.bf
```

## Installation and Invocation (Typescript)

After cloning this repo, cd into its directory and do this:

```sh
$ npm run f
$ npm link
```

Now the interpreter can be invoked from the command line via the 'bfi' command.

Example:

```sh
$ bfi examples/hello-world.bf
```

## About the Language

A brainf*ck language reference can be found [here](http://brainfuck.org/brainfuck.html).

For additional brainf*ck resources, please see:

- Wikipedia page: [here](https://en.wikipedia.org/wiki/Brainfuck)
- The language's page at esolangs.org (esoteric programming languages): [here](https://esolangs.org/wiki/Brainfuck)
- Example source code, and more: [here](http://brainfuck.org/)
- An online interpreter: [here](https://bf.doleczek.pl/)
- An interpreter plus visualizer: [here](https://github.com/fatiherikli/brainfuck-visualizer)
- An x86_64 compiler for Linux: [here](https://github.com/depsterr/bc)
- A brainf*ck 'torture test': [here](https://github.com/rdebath/Brainfuck)

## Notes to self

TODO: When tests are added, add these devDependencies:

```sh
$ npm i -D @babel/core @babel/preset-env @babel/preset-typescript @types/jest jest
```

## License
[MIT](https://choosealicense.com/licenses/mit/)

[build-status-badge-image]: https://circleci.com/gh/tom-weatherhead/lobotomy.svg?style=shield
[build-status-url]: https://circleci.com/gh/tom-weatherhead/lobotomy
[latest-tag-badge-image]: https://badgen.net/github/tag/tom-weatherhead/lobotomy
[latest-tag-url]: https://github.com/tom-weatherhead/lobotomy/tags
[watchers-badge-image]: https://badgen.net/github/watchers/tom-weatherhead/lobotomy
[watchers-url]: https://github.com/tom-weatherhead/lobotomy/watchers
[stars-badge-image]: https://badgen.net/github/stars/tom-weatherhead/lobotomy
[stars-url]: https://github.com/tom-weatherhead/lobotomy/stargazers
[issues-badge-image]: https://badgen.net/github/issues/tom-weatherhead/lobotomy
[issues-url]: https://github.com/tom-weatherhead/lobotomy/issues
[forks-badge-image]: https://badgen.net/github/forks/tom-weatherhead/lobotomy
[forks-url]: https://github.com/tom-weatherhead/lobotomy/network/members
[contributors-badge-image]: https://badgen.net/github/contributors/tom-weatherhead/lobotomy
[contributors-url]: https://github.com/tom-weatherhead/lobotomy/graphs/contributors
[branches-badge-image]: https://badgen.net/github/branches/tom-weatherhead/lobotomy
[branches-url]: https://github.com/tom-weatherhead/lobotomy/branches
[releases-badge-image]: https://badgen.net/github/releases/tom-weatherhead/lobotomy
[releases-url]: https://github.com/tom-weatherhead/lobotomy/releases
[commits-badge-image]: https://badgen.net/github/commits/tom-weatherhead/lobotomy
[commits-url]: https://github.com/tom-weatherhead/lobotomy/commits/master
[last-commit-badge-image]: https://badgen.net/github/last-commit/tom-weatherhead/lobotomy
[last-commit-url]: https://github.com/tom-weatherhead/lobotomy
[types-badge-image]: https://badgen.net/npm/types/lobotomy
[types-url]: https://badgen.net/npm/types/lobotomy
[install-size-badge-image]: https://badgen.net/packagephobia/install/lobotomy
[install-size-url]: https://badgen.net/packagephobia/install/lobotomy
[known-vulnerabilities-badge-image]: https://snyk.io/test/github/tom-weatherhead/lobotomy/badge.svg?targetFile=package.json&package-lock.json
[known-vulnerabilities-url]: https://snyk.io/test/github/tom-weatherhead/lobotomy?targetFile=package.json&package-lock.json
[lines-of-code-badge-image]: https://badgen.net/codeclimate/loc/tom-weatherhead/lobotomy
[lines-of-code-url]: https://badgen.net/codeclimate/loc/tom-weatherhead/lobotomy
[technical-debt-badge-image]: https://badgen.net/codeclimate/tech-debt/tom-weatherhead/lobotomy
[technical-debt-url]: https://badgen.net/codeclimate/tech-debt/tom-weatherhead/lobotomy
[maintainability-badge-image]: https://api.codeclimate.com/v1/badges/00000000000000000000/maintainability
[maintainability-url]: https://codeclimate.com/github/tom-weatherhead/lobotomy/maintainability
[test-coverage-badge-image]: https://api.codeclimate.com/v1/badges/00000000000000000000/test_coverage
[test-coverage-url]: https://codeclimate.com/github/tom-weatherhead/lobotomy/test_coverage
[license-badge-image]: https://img.shields.io/github/license/mashape/apistatus.svg
[license-url]: https://github.com/tom-weatherhead/thaw-grammar/blob/master/LICENSE
