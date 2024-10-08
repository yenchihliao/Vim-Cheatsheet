# Intermediate
Begin to feel the magic of Vim I guess

## motion
* `e`/`E`: go to the end of this word/Word
* `ge`/`gE` : reverse of `e`/`E`
* `0`/`$`: go to the start/end of the line
* `^`  : go to the first non-blank char of line
* `g0`/`g$`/`g^`: similar to `0`/`$`/`^`, but targeting a wrapped line
* `gg`/`G`: **jump** to the start/end of the file
* `<Number>G`/`<Number>gg`: **jump** to nth line

## change (normal-mode)
* `x`/`X`: cut the char under/after cursor
* `s`/`S`: cut the char under/after cursor and enter **insert** mode
* `r`  : replace the char under cursor
* `R` : enter **replace** mode
* `a`  : append(**insert**) after cursor
* `I`/`A`: insert/append(**insert before/after) the line
* `o`/`O` : open a new line below/above and enter **insert** mode
* *`<<`  : add a indent to current line
* *`>>`  : remove a indent from current line
* `v`: enter **visual**(select) mode to select part of code, then use `y` to yank(copy) the selected code

## Insert (insert-mode)
* `Ctrl+n`/`Ctrl+p` : select next/previous option in autocomplete or trigger default autocomplete behavior
* `Ctrl+w`			: delete word before cursor

## Cmdline-mode
press \<enter> after typing
* `:w <fileName>`: overwrite/create fileName
* `:q!` force quit without saving
* `ZZ` : save and quit (= `:x` = `:wq`)
* `ZQ` : force quit without saving (= `:q!`)
* `/<pattern>` : search pattern
* `ctrl-l`: to refresh (can be used to clear searching highlights)
