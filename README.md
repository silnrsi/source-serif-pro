# Important notice regarding this repo

**This fork of Source Serif Pro is intended only to be used as a potential source of Latin-script glyph designs for unrelated non-Latin fonts. It cannot be used to produce viable fonts, as many parts of the fonts and build tools have been renamed, removed, or changed.**

## Notes to those who may use this fork

Please draw only from the `master`, not the `release` branch.

The files in this fork are optimized for use as a source for Latin glyphs for non-Latin fonts:

- All masters of all styles (regular, italic) have the same glyph inventory
- There is a glyph_data.csv file that lists every glyph (look in source)
- The fonts have been enhanced to include glyphs for all [Recommended characters for Non-Roman fonts](https://www.scriptsource.org/entry/gg5wm9hhd3). These have also been fully decomposed to avoid problems with importing only the glyphs needed for this minimal set.

Also:

- Glyphnames are preserved as they were in the original Source Serif Pro sources. You may or may not wish to use those names, although they are generally AGL-compliant. 

**The original README information for Source Serif Pro is retained below, however be aware that most of the information is no longer relevant for this fork.**

# Source Serif Pro

[Source Serif Pro](http://adobe-fonts.github.io/source-serif-pro/)
is a set of OpenType fonts to complement the
[Source Sans Pro](https://github.com/adobe-fonts/source-sans-pro) family.

## Getting involved

[Open an issue](https://github.com/adobe-fonts/source-serif-pro/issues) or send a suggestion to Source Serif's designer [Frank Grießhammer](mailto:opensourcefonts@adobe.com?subject=[GitHub]%20Source%20Serif%20Pro), for consideration.

## Releases

* [Latest release](../../releases/latest)
* [All releases](../../releases)

## Building the fonts from source

### Requirements

To build the binary font files from source, you need to have installed the
[Adobe Font Development Kit for OpenType](https://github.com/adobe-type-tools/afdko/) (AFDKO).

### Building one font

The key to building the OTF fonts is `makeotf`, which is part of the AFDKO toolset.
Information and usage instructions can be found by executing `makeotf -h`. The TTFs
are generated with the `otf2ttf` and `ttfcomponentizer` tools.

Commands to build the Regular style OTF font:

```sh
$ cd Roman/Instances/Regular/
$ makeotf -r -gs -omitMacNames
```

Commands to generate the Regular style TTF font:

```sh
$ otf2ttf SourceSerifPro-Regular.otf
$ ttfcomponentizer SourceSerifPro-Regular.ttf
```

### Building all non-variable fonts

For convenience, a shell script named **build.sh** is provided in the root directory.
It builds all OTFs and TTFs, and can be executed by typing:

```sh
$ ./build.sh
```

### Building the variable fonts

To build the variable TTFs you must install **fontmake** using this command:

```sh
$ pip install fontmake
```

A shell script named **buildVFs.sh** is provided in the root directory.
It generates four variable fonts (two CFF2-OTFs and two TTFs), and can be executed by typing:

```sh
$ ./buildVFs.sh
```
