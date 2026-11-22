# prompt

`prompt` asks the user questions and returns the answers. On a terminal it shows menus that move with the arrow keys and hides passwords as they are typed. When standard input is a pipe, each answer is one line, so a script or a test can supply the answers.

The following example asks for the name and the template of a new project, then asks for confirmation before creating it.

```lus nocheck
local prompt = require("https://atmosp.here/2.0/prompt.lus")

local name = prompt.text("Project name?", { default = "demo" })
local kind = prompt.select("Template?", { "library", "server", "tool" })
if prompt.confirm(`Create $name as a $kind?`, true) then
    print("creating")
end
```

The package requires Lus 2.0 and declares no permissions. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `prompt.lus`, which `lus doc prompt.lus` prints.
