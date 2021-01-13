# pnglatex
`pnglatex` is a small script that turns LaTeX formulas into png images.

    $ pnglatex -f "E=mc^2"

![E=mc^2](https://raw.githubusercontent.com/mneri/pnglatex/master/example.png)

## Installation
Download or clone the repository, then type

    # chmod +x pnglatex
    # cp pnglatex /usr/bin/pnglatex

## Dependencies
`pnglatex` depends on `dvipng`, `imagemagick`, `latex` and `optipng` packages.

## Tips
You can pipe into `pnglatex`:

    $ cat formula.tex | pnglatex

You can generate and open your image with a one-liner:

    $ pnglatex -f "E=mc^2" | xargs eog

Omitting `-f` option will start interactive mode.

    $ pnglatex
    E=mc^2

Logs can give you a good idea of what went wrong.

    $ pnglatex -f "E=mc^2" -l out.log

## Options
+ `-b <color>` Set the background color
+ `-B <color>` Set the border color
+ `-d <dpi>` Set the output resolution to the specified dpi
+ `-e <environment>` Set the environment for the formula (i.e. `displaymath` or `eqnarray`)
+ `-f <formula>` The LaTeX formula
+ `-F <color>` Set the foreground color
+ `-h` Print the help message
+ `-H <file>` Insert the content of the specified file in the preamble
+ `-l <file>` Log file
+ `-m <margin>` Set the margin
+ `-o <file>` Specify the output file name
+ `-O` Optimize the image
+ `-p <packages>` A colon separated list of LaTeX package names
+ `-P <padding>` Set the padding
+ `-s <size>` Set the font size
+ `-S` Don't print image file name
+ `-v` Show version

## Defaults
You can set default options by creating a properties file named `.pnglatex` in your home directory. The
following is an example content:

    BACKGROUND=White
    BORDER=
    DPI=180
    ENVIRONMENT=displaymath
    FOREGROUND=Black
    HEADER=
    MARGIN=
    OPTIMIZE=1
    PACKAGES=amsmath:array
    PADDING=3
    SIZE=11

## Cliptex plugin
This simple plugin allows a quick interaction of pnglatex with the clipboard using
[wl-clipboard](https://github.com/bugaevc/wl-clipboard) (required). You can copy a formula you see anywhere
and then run cliptex `$ cliptex`. This command will substitute the content of the clipboard from the
latex text, to a `png` image using pnglatex. Using ctrl-v will result in pasting an image instead of the
copied text. Suggestion: add a system shortcut to call cliptex (e.g ctrl-q).

Example to substitute tex with an image in a textfield (eq in the browse, like gmail):

    # 1. write tex formula eg in gmail
    # 2. select text
    # ctrl-x
    cliptex # in terminal or ctrl-q (if added to the system shortcuts)
    # ctrl-v

