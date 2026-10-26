# Publishing the dictionaries

The app's catalog points at `https://github.com/buggylaggy/errantant-dictionaries/releases/download/2026-10-25/`. Publish this folder as that release, from inside it:

```sh
gh release create 2026-10-25 --repo buggylaggy/errantant-dictionaries --title "Dictionaries 2026-10-25" --notes-file CREDITS.md \
  oewn.sqlite3.gz wiktionary-en-en.sqlite3.gz wiktionary-fr-fr.sqlite3.gz wiktionary-en-fr.sqlite3.gz wiktionary-de-de.sqlite3.gz wiktionary-en-de.sqlite3.gz wiktionary-es-es.sqlite3.gz wiktionary-en-es.sqlite3.gz wiktionary-it-it.sqlite3.gz wiktionary-en-it.sqlite3.gz wiktionary-pt-pt.sqlite3.gz wiktionary-en-pt.sqlite3.gz wiktionary-ru-ru.sqlite3.gz wiktionary-en-ru.sqlite3.gz wiktionary-tr-tr.sqlite3.gz wiktionary-en-tr.sqlite3.gz wiktionary-ko-ko.sqlite3.gz wiktionary-en-ko.sqlite3.gz wiktionary-ja-ja.sqlite3.gz wiktionary-en-ja.sqlite3.gz jmdict.sqlite3.gz wiktionary-zh-zh.sqlite3.gz wiktionary-en-zh.sqlite3.gz cc-cedict.sqlite3.gz \
  SHA256SUMS CREDITS.md licenses/*.txt
```

Check the hashes before uploading with `sha256sum -c SHA256SUMS`. A rebuilt dictionary is published as a new release:
change the catalog's `release` to the new tag, run `build-dictionary.py release` again and publish it the same way.
