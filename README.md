# DeMANd

Demand is a simple way of documenting directories - similar to what `man` is for programs.

## Specification

A demand file is a file named `.dman` (as *d*irectory *man*). Is should be easily readable via a terminal. A
demand file should always be placed in the folder which contents it describes and for whose programs it provides usage
hints.

Typing the `dman` command in a terminal directory looks up and displays the `.dman` file in the same directory or
recursively in its parent directories. For compatibility reasons if no `.dman` file is found a `README.md` file is looked
up in the same manner.

## Installation instructions

Currently the above mentioned `dman` tool is implemented as an alias which you can add to your `.zshrc` or `.bashrc` file
or similar.

So just copy the contents of the `alias` file to your shell configuration file and start adding `.dman` files to your
directories. You can then call `dman` in the directory or one of its (recursive) child directories to display the content
of the `.dman` file. As mentioned before this also works for `README.md` files in case there is no `.dman` file available.

## Example usage

The idea was born during preparation of a reveal.js presentation. I'm doing this kind of presentations roughly every three
months and always tend to forget how to set up the server.

Therefore I've added a `.dman` file with some hints. It looks like this.

```
Call
        grunt serve --port 8001
to serve in the browser on localhost:8001.

Exchange index.html with yours to switch presentation.

During a presentation you can press ’S’ to switch to presentation mode showing you your notes as well as the next slide
and the presentation time.
```

Simple and definitely highly subjective in its usefulness, but for me it does what it should: telling me how to use the
program(s) contained in this directory and its subdirectories.

When I want to start a presentation I just switch to the folder and call `dman` to get hints about how to set it up.

## Current state and goals

I plan to create a script out of this and make it available via homebrew. Additionally I want to integrate one of the
markdown terminal rendering libraries (like [terminal_markdown_viewer](https://github.com/axiros/terminal_markdown_viewer))
to ease viewing of README.md files where no `.dman` file is found.

I'm not quite sure if I'm doing this to document my own hints and tips on how to use some of the programs I've installed
*or* if this is suitable for a general documentation format as `.dman` files of course don't have to contain just personal
notes. They can also be supplied by the maintainer of a repository for some quick information of how to use it - like a
classic `man` file. As soon as I see the first `.dman` files popping up in the wild I'll probably add support for `.pdman`
(like in *p*ersonal) files. :P