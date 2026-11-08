# Data sources and licenses

The MIT License in `LICENSE` covers the app's code only. The data in `web/` comes from these sources, under their own terms.

## Hebrew and Greek word data and dictionaries (`web/orig/`)

From STEPBible.org, Tyndale House, Cambridge, licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Built from:

- TAHOT: Translators Amalgamated Hebrew Old Testament
- TAGNT: Translators Amalgamated Greek New Testament. Only words found in the NA28-based text are kept. The Greek New Testament translation (`GNT`) is assembled from these same words.
- TBESH and TBESG: Translators Brief lexicons of Extended Strong's for Hebrew and Greek. Definitions are shortened to about 420 characters.

Source: https://github.com/STEPBible/STEPBible-Data

## Cross references (`web/xref/`)

From OpenBible.info, licensed [CC BY](https://creativecommons.org/licenses/by/3.0/). For each verse, the app keeps up to 8 references with at least 3 votes. The data comes via the Scrollmapper Bible Databases project.

## Bible translations (`web/bibles/`)

The texts come from the [Scrollmapper Bible Databases](https://github.com/scrollmapper/bible_databases) project, which gathers public-domain and freely distributable editions. Footnote markers and formatting codes were removed.

Confirm the license of each of these before the store release:

- **Korean (개역성경)**, **Japanese (口語訳 1955)**, **Croatian (Šarić)**: their copyright status is unclear.
- **Berean Standard Bible** and **New Heart English Bible**: free to use; check their current attribution wording.

Translations owned by publishers (ESV, NIV, NLT, NKJV, CSB, NASB) are **not** included. They need a license.
