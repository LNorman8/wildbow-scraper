# _Worm_ Scraper

Scrapes Wildbow's main serials (Worm,Ward,Pact,Pale,Twig) into epub. 

## How to use

First you'll need a modern version of [Node.js](https://nodejs.org/en/). At least v16.13.2 is necessary.

Then, open a terminal ([Mac documentation](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line), [Windows documentation](http://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/)) and install the program by typing

```bash
npm install -g git+https://github.com/LNorman8/wildbow-scraper.git
```

This will take a while as it downloads this program and its dependencies from the internet. Once it's done, try to run it, by typing:

```bash
wildbow-scraper --help
```

If this outputs some help documentation, then the installation process went smoothly. You can move on to assemble the eBook by typing

```bash
wildbow-scraper
```

This will take a while, but will eventually produce a `Worm.epub` file!

If you'd like to get _Ward_ instead of _Worm_, use `--book=ward`, e.g.

```bash
wildbow-scraper --book=ward
```

## EPUB vs. other formats

EPUB is one of the primary eBook formats, but it is not recognized by all readers, including most Amazon Kindle devices. You can use an online converter or other tool to convert EPUB to Kindle MOBI, or any other format.

Alternately, if you are a developer, a pull request adding support for MOBI output would be appreciated; please open an issue to discuss how you plan to proceed.

## Text fixups

This project makes a lot of fixups to the original text, mostly around typos, punctuation, capitalization, and consistency. You can get a more specific idea of what these are via the code; there's [`convert-worker.js`](https://github.com/domenic/worm-scraper/blob/master/lib/convert-worker.js), where some things are handled generally, and [`substitutions.json`](https://github.com/domenic/worm-scraper/blob/master/lib/substitutions.json), for one-off fixes.

This process is designed to be extensible, so if you notice any problems with the original text that you think should be fixed, file an issue to let me know, and we can update the fixup code so that the resulting eBook is improved. (Or better yet, send a pull request!)
