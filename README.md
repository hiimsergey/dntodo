# Declarative Notation for TODOs
How I'm writing TODOs in my coding projects.

## Description
- "TODO" as first word, optional expressions follow
- Expression : one of multiple tags and/or verbal description follows (optional, actually)
    - separation of multiple expressions with "+"
    - `?` finally: option
        - `??`: doubt
- Tag: one word in ALL-CAPS, category of the todo
    - multiple tags in a row: precision, subcategory of the todo
- Description: anything else, although nothing holds you back from using ALL-CAPS too

## EBNF form
```html
<todo> = "TODO" [<expression> {" +" <expression>}]

<expression> = (<tag> | <description> | <tag> <description>)
<tag> = {" " <capital_word>}["?" ["?"]]
<description> = {" " <mixed_word>}

<capital_word> = {<capital_letter>}
<mixed_word> = <non_capital_chacter> {<capital_letter> | <non_capital_character>}
             | <capital_letter> <mixed_word>

<capital_letter> = "A" | "B" | ... | "Z"
<non_capital_character> = "a" | ... | "z" | 1 | ... | 9 | "-" | "_" | "." | ...
```

## Frequently used tags (by me)
| Tag | Meaning |
| -            | -                                                              |
| **CONSIDER** | think about keeping this code                                  |
| **DEBUG**    | debug this part                                                |
| **FINAL**    | do this when you're done with the rest                         |
| **FINISH**   | complete a part that you started                               |
| **MEMORY**   | fix memory management here                                     |
| **MOVE**     | move this code to another place or file                        |
| **NOTE**     | temporary notes in the code                                    |
| **NOW**      | resume here on the next session                                |
| **PLAN**     | description of the structure of the code you're about to write |
| **TEST**     | this code is for testing/debugging, remove later               |
| **VALUE**    | fine tune the value of this variable                           |

## Examples
```c
// TODO
// TODO this doesn't make sense
// TODO CONSIDER using recursion over a loop
// TODO END TEST
// TODO NOW DEBUG wrong value of foo
// TODO TEST + FINISH
/* TODO PLAN
debug the algorithm
write another one
fix the new bug there
consider farming
*/
```
