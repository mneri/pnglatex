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
    PACKAGES=amsmath:amssymb
    PADDING=3
    SIZE=11

Command line provided options override the default options in the `~/.pnglatex` file.

# cliptex Plugin
`cliptex` is a small script that creates LaTeX formulas using the system clipboard.

    $ cliptex

The above command uses the content of the system clipboard to generate a LaTeX formula. The clipboard is then replaced by the
generated image.

## Tips
Bind the script to the <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>C</kbd> key combination. Write your formula direcly in the GMail
editor, select it and strike the key combination. Now press <kbd>Ctrl</kbd> + <kbd>V</kbd> to replace the formula with the
generated image.

## Installation
Download or clone the repository, then type

    # chmod +x cliptex
    # cp cliptex /usr/bin/cliptex

## Dependencies
`cliptex` depends on `pnglatex`, [`wl-clipboard`](https://github.com/bugaevc/wl-clipboard) and `xclip`.

## Options
+ `-h` Print this help message.
+ `-s <session>` Force a session (wayland or x11).
+ `-v` Show version.
