# Editorial

A text editor for your terminal, written in C++17.

**Please note:** This is probably not a replacement for your
editor of choice. It has a pretty small feature set, but I hope that
you find it interesting, at least from a programming standpoint.

## Features

- Syntax highlighting for C++ and Markdown (activated by the file extension),
  with an easy way to add new languages/file types
- Simple scrolling using arrow keys
- File saving/loading, with editing occurring in-memory
- Simple implementation; around 600 lines of C++ code
- Low CPU and memory usage
- Works on any terminal supported by ncurses (essentially anything)

## Key Bindings

**Ctrl-s** : Save the file to disk

**Ctrl-c** : Quit (without saving)

**Left and Right Arrows** : Move cursor one character forward/backward

**Up and Down Arrows** : Move cursor one line up/down

**Tab** : Insert four spaces at the cursor

## Installation

Just run `./build.sh`.

The build script is set up to use `clang++` as the compiler, but you can
easily change this in the build script. Also, be sure that you have
ncurses installed and in a location that your compiler can find.

Most Unix-like systems should already have an ncurses shared library, but
on Windows you will most likely have to install PDCurses, which implements
the same interface as ncurses on Windows platforms. The editor only uses the
most basic features of NCurses (no fancy widgets or anything), so it should be
compatible with PDCurses. However, this has not been tested.

If there is no viable ncurses support for your platform, it should be
straightforward to port over the necessary terminal drawing code. See `screen.h`
and `screen.cpp` for the implementation of the ncurses wrapper.