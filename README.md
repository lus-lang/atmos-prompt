# prompt

Asks questions on the terminal, with arrow key menus and hidden passwords on a terminal and line input through a pipe.

```lus nocheck
local prompt = require("https://atmosp.here/2.0/prompt.lus")

local name = prompt.text("Project name?", { default = "demo" })
local kind = prompt.select("Template?", { "library", "server", "tool" })
if prompt.confirm(`Create $name as a $kind?`, true) then
    print("creating")
end
```

The package requires Lus 2.0. It declares no permissions. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `prompt.lus`. Run `lus doc prompt.lus` to print it.
