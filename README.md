# ipython-tikzmagic

IPython magics for generating figures with TikZ. You can select the output format as svg, png or jpg, define the image size, specify a scale factor, load TikZ packages, and save to external files. The accompanying IPython notebooks shows some examples demonstrating how to use these features.

The package requires a working LaTeX installation and Popple pdftocairo.

This differs from mkrphys's version in that it uses pdftocairo rather that ImageMagick, which due to a security breach has disabled it ability to convert pdf og most distributions. Further SVG are used as default format and SVG's are left at natural size rather then scaling to a fixed pixel size. If desired scaling can be done with either '-sc', '-r', '-s' or '-u' options.

## Installation

```pip install git+git://github.com/mkrphys/ipython-tikzmagic.git```

## Usage

Load package by writing
```
%load_ext tikzmagic
```
in a notebook cell.
Call tikz by prepending `%tikz` to a single command, e.g.,
```
%tikz \draw (0,0) rectangle (1,1);
```
or by starting a cell with `%%tikz`, e.g.,
```
%%tikz
\draw (0,0) rectangle (1,1);
\filldraw (0.5,0.5) circle (.1);
```

## Optional Arguments

- `-sc` or `--scale`: scaling factor of plots, default=1
- `-s` or `--size`: pixel size of plots, e.g., `-s width,height`, Default for png and jpeg is calculated from resolution.
- `-r` or `--resolution` resolution of plots in ppi. Default for png and jpeg is 72.
- `-f` or `--format`: plot format (png, svg or jpg), default=svg
- `-e` or `--encoding`: text encoding, default=utf-8
- `-x` or `--preamble`: LaTeX preamble to insert before tikz figure, default=None
- `-p` or `--package`: LaTeX packages to load, separated by comma, e.g., `-p pgfplots,textcomp`, default=None
- `-l` or `--library`: TikZ libraries to load, separated by comma, e.g., `-l matrix,arrows`, default=None
- `-g` or `--pgfplotslibrary`: Pgfplots libraries to load, separated by comma, e.g., `-l matrix,arrows`, default=None
- `-S` or `--save`: save a copy to file, e.g., -S filename, default=None
- `-u` or `--unit`: Default lenght unit (cm,mm,pt,in,ex,em,pc). If not specified default unit is cm.

## Example

[IPython example notebook](tikzmagic_test.ipynb)
