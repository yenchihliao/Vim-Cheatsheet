# advanced
**BEHOLD** the power of Vim

## motion
* `%`  : go to the corresponding \(, \{, \[
* `*`/`#`: go to next/previous occurrence of the word under cursor
* `f<letter>` : find(go to next occurrence of the) letter
* `t<letter>` : find till(go to just before the occurrence of the) letter
* `F<letter>` : go to previous occurrence of the letter
* `T<letter>` : go to just before the occurrence of the letter before
* `;`/`,`	  : repeat the last f/t/F/T motion forward/backward
* combine `<num><motion>`: Repeat [motion](#motion) num of times.

### jump
* `H`  : **jump** to High position(place the cursor on the top of screen)
* `M`  : **jump** to Middle position(place the cursor at the middle of screen)
* `L`  : **jump** to Low position(place the cursor at the bottom of screen)
* `'<mark>`: **jump** to [mark](#mark)
* `Ctrl+o`: undo jumppings
* `Ctrl+i`: redo jumppings
* `Ctrl+]`: jump to definition(REQUIRE A TAG FILE)
* `Ctrl+t`: reverse previous jump-to-definition behavior(REQUIRE A TAG FILE)
* `g]`    : similar to `Ctrl+]` but choose from list of options
* `:tn`   : jump to the next tag in the list
* `:tp`   : jump to the previous tag in the list

## change (normal-mode)
* `J`  : join lines together
* `gUU`: make the line uppercase
* `guu`: make the line lowercase
* `g~~` : switch case of the line
* `~` : switch case of the letter on cursor
* **Combine**:
	* combine `<num><change>`: Repeat [change](#change) num of times.
	* combine `<change><adjective><position>`: For reduplicated [change](#change) marked with \*(i.g. `y`, `>`, `gU`, `g~` etc.), apply [change](#change) from cursor to position.
		* \<adjective>(optional): `i`: in, `a`: all, \<num>: repeat
		* \<position>: [motion](#motion) or \<num>\<motion> or {, [, (, ), ], }
	* examples:
		- `y$` : yank from the cursor to the end of line
		- `diw`: delete in word(the word touched by cursor)
		- `ca)`: change(delete and enter insert mode) things within \( and \)(included)
		- `2d3w`: delete 3 word twice

## Insert (insert-mode)
* `Ctrl+n`/`Ctrl+p` : select next/previous option in autocomplete or trigger default autocomplete behavior
* `Ctrl+w`			: delete word before cursor
* `Ctrl+t`			: add a indent to current line
* `Ctrl+d`			: remove a indent of current line
* `Ctrl+u`			: delete line before cursor
* `Ctrl+x Ctrl+f`	: autocomplete for file path
* `Ctrl+x Ctrl+]`	: autocomplete for tags(REQUIRE A TAG FILE)
* `Ctrl+x Ctrl+i`	: autocomplete from this and included files

## Cmdline-mode
* `//` : repeat last `/<pattern>`
* `:Ctrl+n`/`:Ctrl+p`: to select next/previous command
* `/Ctrl+n`/`/Ctrl+p`: to select next/previous search
* `:%s/<pattern A>/<pattern B>/g` : substitude all the pattern A in file by pattern B
* `:marks`: list [marks](#mark)
* `:f`: show file path (=`Ctrl+g`)

## mark
* `m<letter>`: mark the line with letter
* `'<mark>`: **jump** to [mark](#mark)
* useful default marks:
    * `'"` : jump to the cursor position last exiting
    * `''` : **jump** back(to the cursor position before jumping)

## register
* macro
	* `q<letter><commands>q` : record actions in the letter register
	* `@<register>` : replay the saved actions once (same as `@@`)
	* `<number>@@` : replay the saved actions N times
* default registers (Useful)
	* `"0`: last yank
	* `"<1~9>`: change history
	* `"%`:fileName
    * `"/`: lastest search
    * `":`: latest command
    * `".`: latest insert
	* `"*`: system clipboard
* techniques:
	* `"ayy`(yank(copy) the current line and store it to register a)
	* `"ap`(paste contents in register a)
    * `@:` : replay last command
    * `@/` : replay last search

## repeating
* `.`  : repeat the last modification to the file

## scrolling
* `zz`/`z.`/`zt`/`zb`: scroll the screen so that the cursor is in the middle/middle/top/bottom of the screen
* `Ctrl+u`/`Ctrl+d` : scroll up/down (half of screen)

## fold
* `zo`/`zO`: fold open
* `zc`/`zC`: fold close
* `zd`: fold delete
* `zR`: open all recusively
* `zM`: close minimize all
* `zf`: create a fold

## window
* `:new`/`:vnew`: new empty window
* `:qa`: close all windows
* `:sp <fileName>`/`:vsp <fileName>`: new window for fileName
* `Ctrl+w v` : split vertical
* `Ctrl+w w` : switch to the other window
* `Ctrl+w k` : move the current window to top
* `Ctrl+w h` : move the current window to left
* `Ctrl+w j` : move the current window to bottom
* `Ctrl+w l` : move the current window to right
* `Ctrl+w |` : maximize window in splitted vertically
* `Ctrl+w _` : maximize window in splitted horizontally
* `Ctrl+w =` : distribute space equally for opened windows

## buffer
* `:e <fileName>`: to add \<fileName\> into buffer
* `:ls`: see all the buffers
* `:bu<num>`/`<num> Ctrl-^`: jump to \<num\> of buffer
* `:bu#`/`# Ctrl-^`: jump to previous buffer
* `:wa`: save all the buffers

## vimdiff

- launch
  - bash
	- `vimdiff [file_left] [file_right]`
	- `vim -d [file_left] [file_right]`
  - vim visual mode
	- `:vertical diffsplit [file_left]`
  - compare existing windows
	- `:windo diffthis`
- cursor
  - `]c` : move to the next difference block
  - `[c` : move to the last difference block
- merge
  - `do` : (diff get) get difference from compared file
  - `dp` : (diff put) put difference to compared file
- misc.
  - vim visual mode
	- `:diffupdate` : update difference between files
	- `:set diffopt=context:<number>` : change the number of lines of context in each difference block
- ref
  - [using vimdiff](https://www.ibm.com/developerworks/cn/linux/l-vimdiff/)

## Issue
- [vim is not remembering last position](http://askubuntu.com/questions/223018/vim-is-not-remembering-last-position/224908#224908)