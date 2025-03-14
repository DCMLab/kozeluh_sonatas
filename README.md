![Version](https://img.shields.io/github/v/release/DCMLab/kozeluh_sonatas?display_name=tag)
[![DOI](https://zenodo.org/badge/388141937.svg)](https://doi.org/10.5281/zenodo.14997015)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/kozeluh_sonatas)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/kozeluh_sonatas](https://github.com/DCMLab/kozeluh_sonatas) and the corresponding
* documentation page [https://dcmlab.github.io/kozeluh_sonatas](https://dcmlab.github.io/kozeluh_sonatas)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/kozeluh_sonatas/introduction).

# Leopold Koželuch – Piano Sonatas (A corpus of annotated scores)

Bohemian composer Leopold Koželuch had a way of repeatedly crossing paths with Mozart. Both composers were successively
offered the same court position in two different instances (by the Archbishop of Salzburg and by Emperor Franz II).
Koželuch's own music is however radically different, with many passages in these sonatas foreshadowing instead the
tragic drama of Beethoven and von Weber. The annotations here investigate the chromatic shocks that support this
tortured expression, incorporating disjunct successions and augmented sonorities that enact a significant break from the
elegant and genteel vocabulary usually associated with Viennese classicism.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/kozeluh_sonatas/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [kozeluh_sonatas.zip](https://github.com/DCMLab/kozeluh_sonatas/releases/latest/download/kozeluh_sonatas.zip)
  * [kozeluh_sonatas.datapackage.json](https://github.com/DCMLab/kozeluh_sonatas/releases/latest/download/kozeluh_sonatas.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/kozeluh_sonatas.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first movement of the sonata in C, op. 8 no. 1, has the following files:

* `MS3/09op08no1a.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/09op08no1a.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/09op08no1a.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/09op08no1a.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/09op08no1a.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/09op08no1a.harmonies.tsv")
notes = ms3.load_tsv("notes/09op08no1a.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/kozeluh_sonatas/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/kozeluh_sonatas/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Leopold Koželuch – Piano Sonatas (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14997015

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## List of piano sonatas

|no |op |op_no|             title             |                     movements                     |root|mode |   year   |pdf|
|--:|--:|----:|-------------------------------|---------------------------------------------------|----|-----|----------|------|
|  1|  1|    1|(1) Sonata 1, F major (1780)   |I. Allegro molto                                   |F   |major|      1780|False |
|  1|  1|    1|(1) Sonata 1, F major (1780)   |II. Cantabile                                      |F   |major|      1780|False |
|  1|  1|    1|(1) Sonata 1, F major (1780)   |III. Rondeau - Presto                              |F   |major|      1780|False |
|  2|  1|    2|(2) Sonata 2, Eb major (1780)  |I. Allegro                                         |Eb  |major|      1780|False |
|  2|  1|    2|(2) Sonata 2, Eb major (1780)  |II. Poco adagio                                    |Eb  |major|      1780|False |
|  2|  1|    2|(2) Sonata 2, Eb major (1780)  |III. Allegro                                       |Eb  |major|      1780|False |
|  3|  1|    3|(3) Sonata 3, D major (1780)   |I. Allegro con brio                                |D   |major|      1780|False |
|  3|  1|    3|(3) Sonata 3, D major (1780)   |II. Poco adagio                                    |D   |major|      1780|False |
|  3|  1|    3|(3) Sonata 3, D major (1780)   |III. Rondeau - Prestissimo                         |D   |major|      1780|False |
|  4|  2|    1|(1) Sonata 4, Bb major (1780)  |I. Allegro                                         |Bb  |major|      1780|False |
|  4|  2|    1|(1) Sonata 4, Bb major (1780)  |II. Adagio                                         |Bb  |major|      1780|False |
|  4|  2|    1|(1) Sonata 4, Bb major (1780)  |III. Allegretto scherzando                         |Bb  |major|      1780|False |
|  5|  2|    2|(2) Sonata 5, A major (1780)   |I. Moderato                                        |A   |major|      1780|False |
|  5|  2|    2|(2) Sonata 5, A major (1780)   |II. Andante                                        |A   |major|      1780|False |
|  5|  2|    2|(2) Sonata 5, A major (1780)   |III. Allegretto                                    |A   |major|      1780|False |
|  6|  2|    3|(3) Sonata 6, C minor (1780)   |I. Largo - Poco presto - Largo                     |C   |minor|      1780|False |
|  6|  2|    3|(3) Sonata 6, C minor (1780)   |II. Allegretto                                     |C   |minor|      1780|False |
|  7|NaN|  NaN|Sonata 7, D major (1780)       |I. Allegro moderato                                |D   |major|      1780|False |
|  7|NaN|  NaN|Sonata 7, D major (1780)       |II. Menuetto & Trio                                |D   |major|      1780|False |
|  7|NaN|  NaN|Sonata 7, D major (1780)       |III. Rondo. Allegro                                |D   |major|      1780|False |
|  8|  5|  NaN|Sonata 8, F major (1781)       |I. Allegro molto                                   |F   |major|      1781|False |
|  8|  5|  NaN|Sonata 8, F major (1781)       |II. Andante con variazioni                         |F   |major|      1781|False |
|  8|  5|  NaN|Sonata 8, F major (1781)       |III. Rondeau - Presto                              |F   |major|      1781|False |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |I. Allegro molto                                   |C   |major|      1784|True  |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |II. Rondo - Andante                                |C   |major|      1784|True  |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |[IIIa Rondeau]                                     |C   |major|      1784|True  |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |[IIIb Allegretto (alternative 3rd movement)]       |C   |major|      1784|True  |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |III. Rondeau                                       |C   |major|      1784|False |
|  9|  8|    1|(1) Sonata 9, C major (1784)   |III. Allegretto (alternative 3rd movement)         |C   |major|      1784|False |
| 10|  8|    2|(2) Sonata 10, F major (1784)  |I. Allegro maestoso                                |F   |major|      1784|True  |
| 10|  8|    2|(2) Sonata 10, F major (1784)  |II. Poco adagio                                    |F   |major|      1784|True  |
| 10|  8|    2|(2) Sonata 10, F major (1784)  |[IIIa Menuetto & Trio]                             |F   |major|      1784|True  |
| 10|  8|    2|(2) Sonata 10, F major (1784)  |III. Aria con variatione (alternative 3rd movement)|F   |major|      1784|True  |
| 10|  8|    2|(2) Sonata 10, F major (1784)  |III. Menuetto & Trio (alternative 3rd movement)    |F   |major|      1784|False |
| 11| 10|    1|(1) Sonata 11, Eb major (1784) |I. Allegro molto                                   |Eb  |major|      1784|True  |
| 11| 10|    1|(1) Sonata 11, Eb major (1784) |[II. Andante]                                      |Eb  |major|      1784|True  |
| 11| 10|    1|(1) Sonata 11, Eb major (1784) |[III. Allegretto]                                  |Eb  |major|      1784|True  |
| 11| 10|    1|(1) Sonata 11, Eb major (1784) |II. Andante                                        |Eb  |major|      1784|False |
| 11| 10|    1|(1) Sonata 11, Eb major (1784) |III. Allegretto                                    |Eb  |major|      1784|False |
| 12| 10|    2|(2) Sonata 12, C major (1784)  |I. Moderato                                        |C   |major|      1784|False |
| 12| 10|    2|(2) Sonata 12, C major (1784)  |II. Andante espressivo                             |C   |major|      1784|False |
| 12| 10|    2|(2) Sonata 12, C major (1784)  |III. Rondeau - Allegretto                          |C   |major|      1784|False |
| 13| 13|    1|(1) Sonata 13, Eb major (1784) |I. Allegro molto                                   |Eb  |major|      1784|False |
| 13| 13|    1|(1) Sonata 13, Eb major (1784) |II. Poco adagio                                    |Eb  |major|      1784|False |
| 13| 13|    1|(1) Sonata 13, Eb major (1784) |III. Rondeau - Presto                              |Eb  |major|      1784|False |
| 14| 13|    2|(2) Sonata 14 in G major (1784)|I. Allegro                                         |G   |major|      1784|True  |
| 14| 13|    2|(2) Sonata 14 in G major (1784)|II. Andante                                        |G   |major|      1784|True  |
| 14| 13|    2|(2) Sonata 14 in G major (1784)|III. Rondeau                                       |G   |major|      1784|True  |
| 15| 13|    3|(3) Sonata 15, E minor (1784)  |I. Allegro molto                                   |E   |minor|      1784|True  |
| 15| 13|    3|(3) Sonata 15, E minor (1784)  |II. Cantabile                                      |E   |minor|      1784|True  |
| 15| 13|    3|(3) Sonata 15, E minor (1784)  |III. Presto                                        |E   |minor|      1784|True  |
| 16| 15|    1|(1) Sonata 16, G minor (1784)  |I. Largo - Allegro molto - Largo                   |G   |minor|      1784|True  |
| 16| 15|    1|(1) Sonata 16, G minor (1784)  |II. Rondeau - Allegro                              |G   |minor|      1784|True  |
| 17| 15|    2|(2) Sonata 17, C major (1785)  |I. Allegro                                         |C   |major|      1785|True  |
| 17| 15|    2|(2) Sonata 17, C major (1785)  |II. Poco adagio                                    |C   |major|      1785|True  |
| 17| 15|    2|(2) Sonata 17, C major (1785)  |III. Presto                                        |C   |major|      1785|True  |
| 18| 15|    3|(3) Sonata 18, Ab major (1785) |I. Andante con Variazioni                          |Ab  |major|      1785|False |
| 18| 15|    3|(3) Sonata 18, Ab major (1785) |II. Allegro molto                                  |Ab  |major|      1785|False |
| 19| 17|    1|(1) Sonata 19, F minor (1785)  |I. Largo                                           |F   |minor|      1785|True  |
| 19| 17|    1|(1) Sonata 19, F minor (1785)  |II. Allegro agitato                                |F   |minor|      1785|True  |
| 19| 17|    1|(1) Sonata 19, F minor (1785)  |III. Finale - Allegretto                           |F   |minor|      1785|True  |
| 20| 17|    2|(2) Sonata 20, A major (1785)  |I. Allegro molto                                   |A   |major|      1785|True  |
| 20| 17|    2|(2) Sonata 20, A major (1785)  |II. Adagio                                         |A   |major|      1785|True  |
| 20| 17|    2|(2) Sonata 20, A major (1785)  |III. Allegro molto                                 |A   |major|      1785|True  |
| 21| 17|    3|(3) Sonata 21, Eb major (1785) |I. Allegro                                         |Eb  |major|      1785|True  |
| 21| 17|    3|(3) Sonata 21, Eb major (1785) |II. Rondeau - Allegretto                           |Eb  |major|      1785|True  |
| 22| 20|    1|(1) Sonata 22, F major (1786)  |I. Allegro                                         |F   |major|      1786|True  |
| 22| 20|    1|(1) Sonata 22, F major (1786)  |II. Adagio                                         |F   |major|      1786|True  |
| 22| 20|    1|(1) Sonata 22, F major (1786)  |III. Rondeau - Allegretto                          |F   |major|      1786|True  |
| 23| 20|    2|(2) Sonata 23, C major (1786)  |I. Allegro                                         |C   |major|      1786|True  |
| 23| 20|    2|(2) Sonata 23, C major (1786)  |II. Adagio                                         |C   |major|      1786|True  |
| 23| 20|    2|(2) Sonata 23, C major (1786)  |III. Rondeau - Allegretto                          |C   |major|      1786|True  |
| 24| 20|    3|(3) Sonata 24, D minor (1786)  |I. Moderato                                        |D   |minor|      1786|True  |
| 24| 20|    3|(3) Sonata 24, D minor (1786)  |II. Poco adagio                                    |D   |minor|      1786|True  |
| 24| 20|    3|(3) Sonata 24, D minor (1786)  |III. Rondeau - Allegretto                          |D   |minor|      1786|True  |
| 25| 26|    1|(1) Sonata 25, D major (1788)  |I. Allegro                                         |D   |major|      1788|True  |
| 25| 26|    1|(1) Sonata 25, D major (1788)  |II. Adagio                                         |D   |major|      1788|True  |
| 25| 26|    1|(1) Sonata 25, D major (1788)  |III. Rondeau - Allegro                             |D   |major|      1788|True  |
| 26| 26|    2|(2) Sonata 26, A minor (1788)  |I. Allegro                                         |A   |minor|      1788|True  |
| 26| 26|    2|(2) Sonata 26, A minor (1788)  |II. Andante con variazione                         |A   |minor|      1788|True  |
| 27| 26|    3|(3) Sonata 27, Eb major (1788) |I. Allegro                                         |Eb  |major|      1788|True  |
| 27| 26|    3|(3) Sonata 27, Eb major (1788) |II. Larghetto alla Siciliana                       |Eb  |major|      1788|True  |
| 27| 26|    3|(3) Sonata 27, Eb major (1788) |III. Rondeau Allegro con Fuoco                     |Eb  |major|      1788|True  |
| 28| 30|    1|(1) Sonata 28, Bb major (1789) |I. Allegro                                         |Bb  |major|      1789|True  |
| 28| 30|    1|(1) Sonata 28, Bb major (1789) |II. Poco adagio                                    |Bb  |major|      1789|True  |
| 28| 30|    1|(1) Sonata 28, Bb major (1789) |III. Rondeau - Allegretto                          |Bb  |major|      1789|True  |
| 29| 30|    2|(2) Sonata 29, G major (1789)  |I. Allegro                                         |G   |major|      1789|True  |
| 29| 30|    2|(2) Sonata 29, G major (1789)  |II. Andante                                        |G   |major|      1789|True  |
| 29| 30|    2|(2) Sonata 29, G major (1789)  |III. Rondeau - Allegretto                          |G   |major|      1789|True  |
| 30| 30|    3|(3) Sonata 30, C minor (1789)  |I. Largo - Allegro - Largo                         |C   |minor|      1789|True  |
| 30| 30|    3|(3) Sonata 30, C minor (1789)  |II. Rondeau - Allegretto                           |C   |minor|      1789|True  |
| 31| 35|    1|(1) Sonata 31, F major (1791)  |I. Allegro                                         |F   |major|      1791|True  |
| 31| 35|    1|(1) Sonata 31, F major (1791)  |II. Adagio                                         |F   |major|      1791|True  |
| 31| 35|    1|(1) Sonata 31, F major (1791)  |III. Rondo - Allegretto                            |F   |major|      1791|True  |
| 32| 35|    2|(2) Sonata 32, A major (1791)  |I. Allegro                                         |A   |major|      1791|True  |
| 32| 35|    2|(2) Sonata 32, A major (1791)  |II. Adagio                                         |A   |major|      1791|True  |
| 32| 35|    2|(2) Sonata 32, A major (1791)  |III. Rondo - Allegro                               |A   |major|      1791|True  |
| 33| 35|    3|(3) Sonata 33, G minor (1791)  |I. Largo - Allegro agitato                         |G   |minor|      1791|True  |
| 33| 35|    3|(3) Sonata 33, G minor (1791)  |II. Allegretto                                     |G   |minor|      1791|True  |
| 34| 38|    1|(1) Sonata 34, Eb major (1793) |I. Allegro                                         |Eb  |major|      1793|False |
| 34| 38|    1|(1) Sonata 34, Eb major (1793) |II. Adagio                                         |Eb  |major|      1793|False |
| 34| 38|    1|(1) Sonata 34, Eb major (1793) |III. Rondeau - Allegro molto                       |Eb  |major|      1793|False |
| 35| 38|    2|(2) Sonata 35, C major (1793)  |I. Allegro                                         |C   |major|      1793|False |
| 35| 38|    2|(2) Sonata 35, C major (1793)  |II. Adagio                                         |C   |major|      1793|False |
| 35| 38|    2|(2) Sonata 35, C major (1793)  |III. Rondeau - Allegretto                          |C   |major|      1793|False |
| 36| 38|    3|(3) Sonata 36, F minor (1793)  |I. Largo - Allegro agitato                         |F   |minor|      1793|True  |
| 36| 38|    3|(3) Sonata 36, F minor (1793)  |II. Allegretto                                     |F   |minor|      1793|True  |
| 37|NaN|  NaN|Sonata 37, G major (?)         |I. Moderato                                        |G   |major|?         |False |
| 37|NaN|  NaN|Sonata 37, G major (?)         |II. Menuetto & Trio                                |G   |major|?         |False |
| 37|NaN|  NaN|Sonata 37, G major (?)         |III. Allegro                                       |G   |major|?         |False |
| 38| 51|    1|(1) Sonata 38, Eb major (1803) |I. Allegro                                         |Eb  |major|      1803|True  |
| 38| 51|    1|(1) Sonata 38, Eb major (1803) |II. Adagio                                         |Eb  |major|      1803|True  |
| 38| 51|    1|(1) Sonata 38, Eb major (1803) |III. Rondo - Vivace                                |Eb  |major|      1803|True  |
| 39| 51|    2|(2) Sonata 39, C minor (1803)  |I. Largo - Allegro molto                           |C   |minor|      1803|True  |
| 39| 51|    2|(2) Sonata 39, C minor (1803)  |II. Rondeau - Allegretto                           |C   |minor|      1803|True  |
| 40| 51|    3|(3) Sonata 40, D minor (1803)  |I. Largo - Allegro molto e agitato                 |D   |minor|      1803|True  |
| 40| 51|    3|(3) Sonata 40, D minor (1803)  |II. Rondeau - Allegretto                           |D   |minor|      1803|True  |
| 41| 55|    1|(1) Sonata 41, G major (1806)  |I. Allegro                                         |G   |major|      1806|True  |
| 41| 56|    1|(1) Sonata 41, G major (1806)  |II. Andante espressivo                             |G   |major|      1806|True  |
| 41| 57|    1|(1) Sonata 41, G major (1806)  |III. Rondo - Allegretto                            |G   |major|      1806|True  |
| 42| 60|    2|(2) Sonata 42, F major (1806)  |I. Poco adagio - Allegro molto                     |F   |major|      1806|True  |
| 42| 61|    2|(2) Sonata 42, F major (1806)  |II. Rondo - Allegretto                             |F   |major|      1806|True  |
| 43|NaN|  NaN|Sonata 43, Eb major (1806)     |I. Allegro                                         |Eb  |major|      1806|False |
| 43|NaN|  NaN|Sonata 43, Eb major (1806)     |II. Rondo - Allegretto                             |Eb  |major|      1806|False |
| 44|NaN|  NaN|Sonata 44, F major (1773)      |I. Allegro                                         |F   |major|      1773|False |
| 44|NaN|  NaN|Sonata 44, F major (1773)      |II. Andante molto con espressione                  |F   |major|      1773|False |
| 44|NaN|  NaN|Sonata 44, F major (1773)      |III. Finale - Presto                               |F   |major|      1773|False |
| 45|NaN|  NaN|Sonata 45, A major (1776)      |I. Arrietta con Variazioni. Andante                |A   |major|      1776|False |
| 45|NaN|  NaN|Sonata 45, A major (1776)      |II. Menuetto - Vivace                              |A   |major|      1776|False |
| 45|NaN|  NaN|Sonata 45, A major (1776)      |III. Rondeau - Allegretto                          |A   |major|      1776|False |
| 46|NaN|  NaN|Sonata 46, C major (?)         |I. Arrietta con Variazioni. Andantino              |C   |major|?         |False |
| 46|NaN|  NaN|Sonata 46, C major (?)         |II. Allegro ma non tanto                           |C   |major|?         |False |
| 47|NaN|  NaN|Sonata 47, Eb major (?)        |I. Adagio                                          |Eb  |major|?         |False |
| 47|NaN|  NaN|Sonata 47, Eb major (?)        |II. Allegro                                        |Eb  |major|?         |False |
| 48|NaN|  NaN|Sonata 48, Bb Major (?)        |I. Adagio maestoso - Allegro molto                 |Bb  |Major|?         |True  |
| 48|NaN|  NaN|Sonata 48, Bb Major (?)        |II. Rondeau - Allegretto                           |Bb  |Major|?         |True  |
| 49|NaN|  NaN|Sonata 49, A major (after 1810)|I. Allegro                                         |A   |major|after 1810|True  |
| 49|NaN|  NaN|Sonata 49, A major (after 1810)|II. Andante sostenuto                              |A   |major|after 1810|True  |
| 49|NaN|  NaN|Sonata 49, A major (after 1810)|III. Rondeau - Allegretto                          |A   |major|after 1810|True  |
| 50|NaN|  NaN|Sonata 50, E minor (after 1810)|I. Adagio - Allegro molto con fuoco                |E   |minor|after 1810|True  |
| 50|NaN|  NaN|Sonata 50, E minor (after 1810)|II. Larghetto                                      |E   |minor|after 1810|True  |
| 50|NaN|  NaN|Sonata 50, E minor (after 1810)|III. Rondo - Presto                                |E   |minor|after 1810|True  |

## File naming convention

```regex
(?<sonata>\d{2})
op(?<op>\d{2})
no(?<no>\d)
(?<movement>a|b|c)
```


## Overview
|file_name |measures|labels|standard| annotators |
|----------|-------:|-----:|--------|------------|
|09op08no1a|     135|   272|2.1.0   |Adrian Nagel|
|09op08no1b|      67|   149|2.1.0   |Adrian Nagel|
|10op08no2a|     155|   350|2.1.0   |Adrian Nagel|
|10op08no2b|      73|   171|2.1.0   |Adrian Nagel|
|10op08no2c|     156|   493|2.1.0   |Adrian Nagel|
|11op10no1a|     177|   493|2.1.0   |Adrian Nagel|
|14op13no2a|     171|   213|2.1.0   |Adrian Nagel|
|14op13no2b|      49|   153|2.1.0   |Adrian Nagel|
|14op13no2c|      93|   193|2.1.0   |Adrian Nagel|
|15op13no3a|     137|   373|2.1.0   |Adrian Nagel|
|15op13no3b|      84|   234|2.1.0   |Adrian Nagel|
|15op13no3c|     141|   360|2.1.0   |Adrian Nagel|
|16op15no1a|      34|   111|2.1.0   |Adrian Nagel|
|16op15no1b|     208|   524|2.1.0   |Adrian Nagel|
|16op15no1c|     186|   523|2.1.0   |Adrian Nagel|
|17op15no2a|     201|   527|2.1.0   |Adrian Nagel|
|17op15no2b|      40|   140|2.1.0   |Adrian Nagel|
|17op15no2c|     160|   385|2.1.0   |Adrian Nagel|
|19op17no1a|      37|   123|2.1.0   |Adrian Nagel|
|19op17no1b|     255|   516|2.1.0   |Adrian Nagel|
|19op17no1c|     213|   345|2.1.0   |Adrian Nagel|
|20op17no2a|     226|   608|2.1.0   |Adrian Nagel|
|20op17no2b|     100|   291|2.1.0   |Adrian Nagel|
|20op17no2c|     218|   482|2.1.0   |Adrian Nagel|
|21op17no3a|     193|   543|2.1.0   |Adrian Nagel|
|21op17no3b|     219|   589|2.1.0   |Adrian Nagel|
|22op20no1a|     171|   291|2.1.0   |Adrian Nagel|
|22op20no1b|      45|   124|2.1.0   |Adrian Nagel|
|22op20no1c|     150|   267|2.1.0   |Adrian Nagel|
|23op20no2a|     134|   495|2.1.0   |Adrian Nagel|
|23op20no2b|      51|   150|2.1.0   |Adrian Nagel|
|23op20no2c|     143|   329|2.1.0   |Adrian Nagel|
|24op20no3a|     152|   351|2.1.0   |Adrian Nagel|
|24op20no3b|      50|   121|2.1.0   |Adrian Nagel|
|24op20no3c|     159|   453|2.1.0   |Adrian Nagel|
|25op26no1a|     216|   514|2.1.0   |Adrian Nagel|
|25op26no1b|      50|   153|2.1.0   |Adrian Nagel|
|25op26no1c|     178|   240|2.1.0   |Adrian Nagel|
|26op26no2a|     225|   473|2.1.0   |Adrian Nagel|
|26op26no2b|     174|   482|2.1.0   |Adrian Nagel|
|27op26no3a|     204|   555|2.1.0   |Adrian Nagel|
|27op26no3b|      54|   169|2.1.0   |Adrian Nagel|
|27op26no3c|     213|   246|2.1.0   |Adrian Nagel|
|28op30no1a|     152|   344|2.1.0   |Adrian Nagel|
|28op30no1b|      50|   185|2.1.0   |Adrian Nagel|
|28op30no1c|     207|   457|2.1.0   |Adrian Nagel|
|29op30no2a|     195|   405|2.1.0   |Adrian Nagel|
|29op30no2b|      39|   159|2.1.0   |Adrian Nagel|
|29op30no2c|     206|   474|2.1.0   |Adrian Nagel|


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
