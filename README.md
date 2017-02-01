# pnglatex
`pnglatex` is a small script that turns LaTeX formulas into png images. It's as simple as:

    ./pnglatex -f "E=mc^2"

## Installation
Download or clone the repository and make it executable, using

    chmod +x pnglatex

## Options
+ `-b <color>` Set the background color
+ `-B <color>` Set the border color
+ `-d <dpi>` Set the output resolution to the specified dpi
+ `-e <environment>` Set the environment for the formula (i.e. `displaymath` or `eqnarray`)
+ `-f <formula>` The LaTeX formula
+ `-F <color>` Set the foreground color
+ `-h` Print the help message
+ `-H <header>` Input file in header
+ `-m <margin>` Set the margin
+ `-M` Strip meta information
+ `-o <file>` Specify the output file name
+ `-O` Optimize the image
+ `-p <packages>` A colon separated list of LaTeX package names
+ `-P <padding>` Set the padding
+ `-s <size>` Set the font size
+ `-S` Don't print image file name
+ `-v` Show version
