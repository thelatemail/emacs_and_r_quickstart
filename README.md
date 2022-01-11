# Emacs and R quickstart

A quick start guide for Emacs for R users, for people that have never used Emacs, and don't care about all the non-R functionality.

I don't care if this isn't complete, or covers every point. It works. End of story.

# Install the software

If you're a Windows user and not a masochist, use Vincent Goulet's excellent installer to get Emacs+ESS (Emacs Speaks Statistics) https://vigou3.gitlab.io/emacs-modified-windows/ installed.  
If you're on some flavour of Linux, load up your favourite package manager and grab the Emacs and ESS packages.

# Basic shortcut starting points

Some basic info to get you started, and to make sense of the keyboard shortcuts used here and elsewhere when discussing Emacs.  
`C-` = hold the Control/Ctrl key.  
e.g., `C-c` means Ctrl-c

`M-` = hold the 'Meta' key, otherwise known as Alt on a normal person's keyboard  
e.g., `M-x` means Alt-x

# Copying and pasting

You're not going to get very far without copying and pasting from Stackoverflow. So:

`M-w` = copy  
`C-w` = cut  
`C-y` = paste (yank)  

# I hit the wrong shortcut and I've ruined everything

`C-g` (quit) repetitively until there's no more issue. Go ahead and spam it `C-g C-g C-g C-g`, it won't do any harm.

# Starting R

Assuming you have both R and Emacs installed, type `M-x R`
Boom, you have an R session running in Emacs.

## Opening a script

`C-x C-f` and type the path to a script and hit enter - remember you can use tab completion to avoid typing every letter.  
If you hit enter on a directory rather than a file, you can use the arrow keys and Enter to navigate to a file.

## Opening multiple windows

Now, you almost certainly don't want everything in 1 window and have to keep switching back and forth. Luckily you don't have to:  
`C-x 3` will split vertically
`C-x 2` will split horizontally
`C-x 1` will return to one window
`C-x 0` will delete the current split you're working in


