## Repro for Biome issue

Settings for `useFilenamingConvention`:

```json
{
  "linter": {
    "rules": {
      "style": {
        "useFilenamingConvention": {
          "level": "error",
          "options": {
            "strictCase": true,
            "requireAscii": true,
            "filenameCases": ["camelCase", "export"]
          }
        }
      }
    }
  }
}
```

Remix has route files like this `app/routes/$.tsx` and Biome errors on it:

```
The filename should be in camelCase or equal to the name of an export.
```

That `$.tsx` can’t really be camelCased no matter what. Should filenames like this be ignored?

Remix also has routes like this that are caught in the error: `app.$foo.$bar.tsx`.
