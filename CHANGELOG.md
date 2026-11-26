# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `prompt`.

- Added the `prompt` package.
  - `prompt.text`: Asks for a line of text.
  - `prompt.password`: Asks for a secret that the terminal does not show.
  - `prompt.confirm`: Asks a yes or no question.
  - `prompt.number`: Asks for a number within optional bounds.
  - `prompt.select`: Asks for one of a list of choices.
  - `prompt.multiselect`: Asks for any number of a list of choices.
  - `prompt.use`: Replaces the input and the output of every prompt.
  - `prompt.iscancel`: Returns `true` for the error object of a cancelled prompt.
