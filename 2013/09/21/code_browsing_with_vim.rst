code browsing with vim
======================



.. author:: default
.. categories:: none
.. tags:: vim, ctags
.. comments::

I use vim as my primary editor and I love it. I quite frequently have moments
when I say to myself "Wow! I didn't know I can also do this in vim". One such thing
I recently discovered is the usage of ctags with vim.
ctags is a program which generate tag files for files. The tag files lets us
jump to different sections of code very fast.
When I was working on visual studio during my intern I particularly liked the
"Go To Definition" feature on right click, which is very useful while reading
a long code file. It simply takes you to the area of code where that particular
function or variable is defined.
With ctags and vim I can do the same in a more efficient manner, without even
touching the mouse.

Add this line I found on stackoverflow to your `~/.vimrc` and it will generate tag file everytime you save your code

`au BufWritePost *.c,*.cpp,*.h,*py silent! !ctags -R --fields=+l &`

Then use <C-]> to go to the tag of your cursor is present and <C-T> to go back
to the
place you came from.

Type `:help tag` in normal mode for more information on tags.

Happy Vimming :)
