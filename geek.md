# Geek
Niche features in my POV

## command:
* `:!<command>` : execute command in shell
* `:!!` : repeat last `!<command>`
* `/<pattern>/<offset>` : search pattern and place cursor on offset
* `:&<flag>` : repeat last `s/<pattern A>/<pattern B>/` with flag
* `:~<flag>` : use last `/<pattern>` as pattern A and last `:s` pattern B with flag
* `:g/<pattern>/<command>/` : execute command at lines that match pattern
* `:sh` : go to shell. come back by `$exit`
* notes:
	* `<offset>`:
		* +-n: move n lines
		* b+-n: n char from begin of word
		* e+-n: n char from end of word
	* `<flag>`:
		* `g` : apply to all matches
		* `&` : use previous flag
		* `c` : comfirm needed
		* `i` : ignore case
		* `I` : don't ignore case
	* replace string(`<pattern B>`):
		* `&` : `<pattern A>`
		* `~` : previos `<pattern B>`
		* `\<num>` : pattern within ()

## Insert:
* `Ctrl+v` : insert the hidden character such as <ESC>, <CR>, etc.
* `Ctrl+r <register>`: insert from \<register>
* `Ctrl+a`: insert last inserted text(equivalent to `^r.`)
* `Ctrl+@`: insert last text and leave insert mode(equivalent to `^a<esc>`)

## Undo:
* `U`: undo the line on the cursor(This also count as a change. Hence, use `u` to redo `U`)
* (Please use mundo plugin...)`g+`/`g-`: change the current text to the next/previous text in undo tree

## scrolling
* `Ctrl+f`/`Ctrl+b` : scroll up(forward)/down(backward) (full screen)

## Visual block
Edit multiple lines at the same time
* step1: press `Ctrl+v`
* step2: select multiple lines as if in visual mode
* step3: edit ONLY the first line
* step4: press `<ecs>`
* step5: be amazed