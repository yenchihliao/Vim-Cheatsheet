# Beginner
At least make Vim usable... Enjoy the pain

## motion
* (try not to navigate with direction keys) ← → ↑ ↓
* `h`/`j`/`k`/`l`: ←/↓/↑/→
* `b`/`B`: go to the start of the previous word/Word
* `w`/`W`: go to the start of the following word/Word

## change (normal-mode)
* `i`: switch to **insert-mode** under the cursor
* *`yy`/`Y`: yank(copy) a line with/without last \r
* *`dd`/`D`: delete(cut) a line with/without last \r
* *`cc`/`C`: change(cut and enter **insert mode**) a line
* `p`/`P`: paste yanked or cut things under/before cursor

## Insert (insert-mode)
* `<ECS>`/`Ctrl+[`: back to **normal** mode when you done typing

## Cmdline-mode
press \<enter> after typing
* `:w`: write(save) the file
* `:q`: quit
* `:x`: save and quit(=`:wq`)

## Undo
* `u`: undo
* `ctrl-r`: redo