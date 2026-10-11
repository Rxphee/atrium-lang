# atrium-lang

Translations for the user interface of [atrium](https://github.com/Rxphee/atrium).

| Folder   | Used by                      |
| -------- | ---------------------------- |
| `admin/` | Admin interface              |
| `site/`  | Fixed texts of the websites  |

Each folder holds one JSON file per language (`de.json`, `en.json`) with flat message ids as keys and ICU messages as values:

```json
{
    "footer.imprint": "Impressum"
}
```

`admin/intl-update.sh` and `site/intl-update.sh` in the atrium repository clone this repository into `lang/`. That folder is deleted on every run, so translations must be changed here, never there.

A message without a translation falls back to the `defaultMessage` in the code. Page content is not translated here; it lives in the page tree of each language.
