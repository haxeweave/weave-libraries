# Weave library index

Libraries checked to work in [Weave](https://github.com/haxeweave) games.
Weave lists them in **Project Settings ▸ Libraries ▸ Add from the Weave
library index**, fetches the one you pick at the version named here, and
checks it again when it arrives.

This repository holds links, not code: each entry in `index.json` names a
library's git repository and the tag or commit it is pinned to. A Haxe
library is compiled into the game; a C library (`"kind": "native"`) is bound
from the header named in `"header"`, as **New from a C header…** binds one.

## An entry

```json
{
	"name": "actuate",
	"kind": "haxe",
	"description": "Tweening with chained calls.",
	"git": "https://github.com/openfl/actuate.git",
	"ref": "1.9.0",
	"license": "MIT",
	"dependencies": [],
	"verdict": "yes",
	"summary": "compiles for the web and for native",
	"checked": "2026-10-13",
	"commit": "…"
}
```

`verdict`, `summary`, `checked` and `commit` are written by the check, not by
hand: in a Weave checkout, `node scripts/library-index.mjs <path>/index.json
--write`. The verdict is `yes` (works on the web and natively), `partly`
(some modules cannot be used; the summary says which and why), `native only`
or `web only`. An entry that does not work is not listed.

## Adding a library

1. Pin it to a tag, or to a commit when the repository has no tags.
2. Run the check above and read what it says.
3. Open a pull request with the entry and the check's result.

Weave's own tests fetch this index and check every entry against the engine
of the day, so a library that stops working is found there.
