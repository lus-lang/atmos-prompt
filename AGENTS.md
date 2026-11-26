# AGENTS.md

`lus-lang/atmos-prompt` is the repository of the `prompt` package of the atmosphere registry. Programs load the package with `require("https://atmosp.here/2.0/prompt.lus")`.

## Scope

`prompt` asks the user questions and returns the answers. On a terminal it shows menus that move with the arrow keys and hides passwords as they are typed. When standard input is a pipe, each answer is one line, so a script or a test can supply the answers. The public API is every function that `prompt.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `prompt.lus` is the whole package. Its header doc comment contains the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load `prompt.lus` from the parent of `TEST_DIR`, the directory that holds the test file.

## Dependencies

- `color`, which `prompt.lus` loads by its atmosphere URL

The tests load `color` from a checkout of `lus-lang/atmos-color` next to this repository, so clone it into the same parent directory first.

## Commands

Run these commands from the root of the repository.

```sh
lus test tests          # run the tests
lus check prompt.lus     # lint
lus doc prompt.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header.
- Prose follows the `lus-writing` skill, which `lus agents init` installs and https://lus.dev/agents/skills/lus-writing/SKILL.md serves. In particular, prose has no dashes or semicolons and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
