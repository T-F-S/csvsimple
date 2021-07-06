# Changelog
All notable changes to this project will be documented in this file.

The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to
[Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
### Changed
### Deprecated
### Removed
### Fixed
### Security


## [2.1.0] - 2021-07-06

### Added
- Support for (limited) data collection (issue #15)
- Support for package `tabularray` (part of issue #12)
- Option `after filter`
- Option `collect data`
- Option `data collection`
- Option `tabularray`
- Option `centered tabularray`
- `\csvdatacollection`
- `\csvexpval`
- `\csvexpnot`
- `\csvcollectn`
- `\csvcollectx`
- `\csvcollectV`

### Fixed
- Line Range was not resetted
- Wrong link and word inside documentation `csvsimple.pdf` (issue #13, issue #15)
- Several inconsistent local/global assignment errors



## [2.0.0] - 2021-06-29

### Added
- New documentation `csvsimple-l3.pdf` for the new LaTeX3 version
  (revised, adapted and extended from the old documentation)
- `\thecsvcolumncount`
- Option `autotabular*`
- Option `autobooktabular*`
- Option `autolongtable*`
- Option `autobooklongtable*`
- Option `filter bool`
- Option `filter fp`
- Option `range`
- `\csvautotabular*`
- `\csvautobooktabular*`
- `\csvautolongtable*`
- `\csvautobooklongtable*`
- `\csvfilterbool`
- `\ifcsvfirstrow`
- `\ifcsvoddrow`
- `\ifcsvfpcmp`
- `\ifcsvintcmp`
- `\csvsortingrule`

### Changed
- Complete re-implementation of the hitherto existing latex package
  as LaTeX3 package using the expl3 interface. From now on, three package
  files are provided:
  ** `csvsimple-legacy.sty`   identical to csvsimple until version 1.22  **
  ** `csvsimple-l3.sty`       LaTeX3 package of csvsimple                **
  ** `csvsimple.sty`          stub to select `l3` or `legacy` (default)  **
- The LaTeX2e version (`csvsimple-legacy`) will be maintained in its
  current state with no intended changes with exceptions of bug fixes.
- The LaTeX3 version (`csvsimple-l3`) is regarded to be the main package
  and may receive feature upgrades in the future
- Existing documents using csvsimple v1.22 need no change since loading
  `csvsimple` will load `csvsimple-legacy`.
- `cvsimple-l3` is a *nearly* drop-in replacement for `csvsimple-legacy`.
  Only very few things phased out and the user interface is quite identical.
  The most significant difference is that `l3keys` are used instead of `pgfkeys`
  which may need adaptions on user side (for examples, if .styles are used)
- New documents are encouraged to apply `cvsimple-l3` instead of `csvsimple-legacy`.
- For the complete package is valid: do not upgrade from version 1.22, if your
  TeX installation has no current LateX3/expl3 support a.k.a *is too old*
- `csvinputline` and `csvrow` are no longer LaTeX2e counters
- The hitherto existing documentation `csvsimple.pdf` is now `csvsimple-legacy.pdf`
- `csvsimple.pdf` documents the stub package and differences
  between `csvsimple-l3.sty` and `csvsimple-legacy.sty`
- `column count = 0` means automatic column number detection for CSV files without head
- Option `head` does not change option `check column count` anymore
- Changelog moved from CHANGES to CHANGES.md and adapted to
  [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
- From now on version numbers adhere to
  [Semantic Versioning](http://semver.org/spec/v2.0.0.html)

### Deprecated
- `\csviffirstrow`
- `\csvifoddrow`

### Removed
- `\csvheadset`
- Option `filter`
- Option `nofilter`
- Option `nohead`



## [1.22] - 2021-06-07

### Added
- Option `head to column names prefix` (issue #7)

### Changed
- Due to changes in the LaTeX kernel 2021-06-01, the empty line
  detection of csvsimple had to be adapted. Updating csvsimple is
  essential to avoid problems with kernel 2021-06-01. (issue #11)



## [1.21] - 2019-04-09

### Changed
- Package `pgfrcs` added as required package
- Introduction augmented with additional hints for first time users (issue #3)

### Fixed
- Spurious blank in sorting code removed



## [1.20] - 2016-07-01

### Added
- New string comparison macros:
- `\ifcsvstrequal`
- `\ifcsvprostrequal`
- `\ifcsvstrcmp`
- `\ifcsvnotstrcmp`
- New filter options:
- Option `filter ifthen`
- Option `filter test`
- Option `filter expr`
- Option `full filter`
- Option `filter strcmp`
- Option `filter not strcmp`

### Changed
- Implementation changed from `\roman` to `\romannumeral`
- `\write18` replaced by `\ShellEscape` from the shellesc package
- `\csvlinetotablerow` implemented more efficiently
- `\csvloop` made long
- Code optimizations
- Documentation revised



## [1.12] - 2014-07-14

### Added
- Option `csvsorter token`
- Documentation extended with siunitx examples

### Changed
- Success of CSV-Sorter call is checked (Note: Update to CSV-Sorter v0.94 or newer!)
- Encircling column entry braces removed for all entries for better siunitx compatibility
- Documentation revised

### Fixed
- CSV-Sorter call incompatibilities with the ngerman package (not babel)



## [1.11] - 2014-07-08

### Changed
- If a CSV file with an empty first line is found, csvsimple
  stops with an error message

### Fixed
- Sorting preprocessor overwrites the input data in some combinations



## [1.10] - 2014-07-07

### Added
- `\csvautobooktabular`
- `\csvautobooklongtable`
- External sorting specifically supported for the CSV-Sorter tool with the new options
- Option `csvsorter command`
- Option `csvsorter configpath`
- Option `csvsorter log`
- Option `sort by`
- Option `new sorting rule`
- New keys for respecting special characters:
- Option `respect tab`
- Option `respect percent`
- Option `respect sharp`
- Option `respect dollar`
- Option `respect and`
- Option `respect backslash`
- Option `respect underscore`
- Option `respect tilde`
- Option `respect circumflex`
- Option `respect leftbrace`
- Option `respect rightbrace`
- Option `respect all`
- Option `respect none`
- Option setting `separator = tab`

### Changed
- If a CSV file is not found, csvsimple stops with an error message instead of a warning

### Fixed
- Table head names in curly brackets were not recognized for some cases



## [1.07] - 2013-09-25

### Added
- Option `separator` to set the data value separator to
  `comma`, `semicolon`, or `pipe`

### Changed
- Internal macro `\TrimSpaces` renamed to avoid name clashed with `xparse`



## [1.06] - 2012-11-08

### Changed
- Implementation for line breaking changed from full macro expansion to
  token expansion. This allows quite arbitrary macro code inside the data.
  Note that this may be a breaking change if your application expects
  expanded column values.
- Option values added for `\csvautotabular` and `\csvautolongtable`



## [1.05] - 2012-03-12

### Added
- Source code of the documentation added
- Provision of the csvsimple.tds.zip file for easier installation
- Option `preprocessed file`
- Option `preprocessor`
- Option `no preprocessing`

### Changed
- Documentation language changed from German to English
- Option `nocheckcolumncount` renamed to `no check column count`
- Option `nofilter` renamed to `no check column count`
- Option `nocheckcolumncount` renamed to `no filter`
- Option `nohead` renamed to `no head`

### Deprecated
- Option `nofilter`
- Option `nohead`

### Removed
- Option `@table` removed from the documentation

### Fixed
- Error in `nocheckcolumncount` corrected and key renamed to 'no check column count'



## [1.04] - 2011-11-11

### Added
- Option `head to column names` (automatic column names)
- Option `no table`
- Column numbers can now be used for column macro definitions

### Changed
- Internal behaviour of `before reading` and `after reading`
  changed for tables

### Fixed
- documentation update and correction



## [1.03] - 2011-11-04

### Fixed
- Processing error for lines starting with '00' corrected



## [1.02] - 2011-04-04

### Added
- `\csvfilteraccept`
- `\csvfilterreject`
- Option `filter accept all`
- Option `filter reject all`

### Fixed
- Error in the documentation for longtable und tabbing corrected



## [1.01] - 2010-11-10

### Added
- Option `after first line`
- Option `late after first line`
- New example for key evaluation in the documentation

### Changed
- Documentation of some options clarified



## [1.00] - 2010-07-28

### Added
- Initial public release
