# pnglatex
`pnglatex` is a small script that turns LaTeX formulas into png images.

    $ pnglatex -f "E=mc^2"

![E=mc^2](https://raw.githubusercontent.com/mneri/pnglatex/master/example.png)

If the image was created using `pnglatex` you can get the original formula running:

    $ pnglatex -r formula.png
    E=mc^2

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
    Interactive mode (<Ctrl-D> to end):
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
+ `-M` Strip meta information
+ `-o <file>` Specify the output file name
+ `-O` Optimize the image
+ `-p <packages>` A colon separated list of LaTeX package names
+ `-P <padding>` Set the padding
+ `-r <file>` Read an image and print the LaTeX formula
+ `-s <size>` Set the font size
+ `-S` Don't print image file name
+ `-v` Show version
