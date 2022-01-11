# Emacs and R quickstart

A quick start guide for Emacs for R users, for people that have never used Emacs, and don't care about all the non-R functionality.

I'm basically going to walk through from starting, to setting up a workspace, to doing something useful, in order.

I don't care if this isn't complete, or covers every point in infinite detail. This will work enough to get you started, and cover some of the most obvious niggles an R user new to Emacs will run up against. There are a plethora of more complicated guides to using the full power of Emacs, which can be explored after getting started as specific issues arise.

# Install the software

If you're a Windows user and not a masochist, use Vincent Goulet's excellent installer to get Emacs+ESS (Emacs Speaks Statistics) https://vigou3.gitlab.io/emacs-modified-windows/ installed.  
If you're on some flavour of Linux, load up your favourite package manager and grab the Emacs and ESS packages.

# Basic shortcut starting points

Some basic info to get you started, and to make sense of the keyboard shortcuts used here and elsewhere when discussing Emacs.  
`C-` = hold the Control/Ctrl key.  
e.g., `C-c` means Ctrl-c

`M-` = hold the 'Meta' key, otherwise known as Alt on a normal person's keyboard  
e.g., `M-x` means Alt-x

## I hit the wrong shortcut and I've ruined everything

`C-g` (quit) repetitively until there's no more issue. Go ahead and spam it `C-g C-g C-g C-g`, it won't do any harm.

# Starting an R session

Assuming you have both R and Emacs installed, type `M-x R`
Boom, you have an R session running in Emacs.

## Opening a script

`C-x C-f` and type the path to a script and hit enter - remember you can use tab completion to avoid typing every letter.  
If you hit enter on a directory rather than a file, you can use the arrow keys and Enter to navigate to a file.  
If the filename you've entered doesn't exist, Emacs will create a 'buffer' which when saved will write to the specified location.

## Opening multiple windows

Now, you almost certainly don't want everything in 1 window and have to keep switching back and forth. Luckily you don't have to:  
`C-x 3` will split vertically  
`C-x 2` will split horizontally  
`C-x 1` will return to one window  
`C-x 0` will delete the current split you're working in  

Resizing horizontal splits is obvious, grab that divider and drag away. Not so much vertical splits. There's a tiny little grey dividing line at the bottom of the total Emacs window which you can use to resize. See the image below.

![Alt](/03-resize_horizontal.png "Resizing horizontally")


## Switching between windows and buffers

`C-x o` (that's oh, not zero) will cycle through the windows you currently have open.  
If you want to change which 'buffer', or content, is shown in the current window, `C-LEFT` (LEFT = left arrow key) and `C-RIGHT` (RIGHT = right arrow key) will cycle through what you have open. You can have multiple views of the same content open in any window if you so desire. This can be handy if you want to see the header and footer of the same file at the same time, for instance.

## Typing, copying and pasting

You're not going to get very far without copying and pasting from Stackoverflow. So:

`M-w` = copy  
`C-w` = cut  
`C-y` = paste (yank)  

## Running code

### At the prompt
If you're in the \*R\* window, just use R like you normally would. Type at the prompt and hit enter to evaluate code.

If you want to re-run or edit previously entered code:  
`C-p` = cycle backwards to *previous* submissions  
`C-n` = cycle forward to *next* submissions  

`TAB` completion still works like it does in any other R instance.

### In an .R script

There's shortcuts for running lines, paragraphs, functions, etc from a script. But in the short-term, there is one shortcut to rule them all.  
Highlight the code you want to run and `C-c`  



