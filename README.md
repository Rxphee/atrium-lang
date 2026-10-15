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

Every message in the code needs an entry in both `de.json` and `en.json`. `en.json` repeats the `defaultMessage` from the code. `npm run lint` and the pre-commit hook in the atrium repository fail if a message is missing (`check-translations.js`), and warn about entries that are no longer used or an English text that differs from the code.

## Adding or changing a text

1. Add the message to `de.json` and `en.json` of the package, sorted by id, and push to `main` (no pull request needed).
2. Run `./intl-update.sh` in `admin/` or `site/` of the atrium repository, then commit the code.

Remove entries once the code no longer uses them. A message without a translation falls back to the `defaultMessage` in the code. Page content is not translated here; it lives in the page tree of each language.
