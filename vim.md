# VIM

- Moving around:
	- h (left)
	- j (down)
	- k (up)
	- l (right)
 - To start vim from shell: `vim FILENAME <ENTER>`
- To exit Vim type:
	- `<ESC> :q! <ENTER>`to trash all changes
	- `<ESC> :wq! <ENTER>` to save the changes
- To delete at the character at the cursor type: `x`
- To insert or append text type:
	- `i "type inserted tex" <ESC>` to insert before the cursor
	- `A "type appended text" <ESC>` to append after th line
- Pressing `<ESC>` will place you in Normal mode or will cancel an unwanted and partially completed command. 

- To delete form the cursor up to the next word type: 		`dw`
- To delete from the cursor to the end of a line type: 		`d$`
- To delete a whole line type: `dd`
- To repeat a motion prepend it with a number: `2w`
- The format for a change command is: 
	- `operator 	[number] 	motion`
- Where :
	- `operator` - is what to do, such as `d` for delete
	- `[number]` - is an optional count to repeat the motion
	- `motion` - moves over the textto operate on, such as `w` (word), `$` (to the end of line), etc
- To move to the start of the line use a zero: `0` 
- To undo 
	- Previous actions, type: `u` (lowercase u )
	- All the changes on a line, type `U` (capital U)
	- The undo's, type `CTRL-R`
						