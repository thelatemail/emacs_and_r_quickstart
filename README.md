# Emacs and R quickstart

A quick start guide for Emacs for R users, for people that have never used Emacs, and don't care about all the R-irrelevant functionality.

I'm basically going to walk through from starting, to setting up a workspace, to doing something useful, in order.

I don't care if this isn't complete, or covers every point in infinite detail. This will work enough to get you started, and cover some of the most obvious niggles an R user new to Emacs will run up against. There are a plethora of more complicated guides to using the full power of Emacs, which can be explored as specific issues arise.

# Install the software

If you're a Windows user and not a masochist, use Vincent Goulet's excellent installer ( https://vigou3.gitlab.io/emacs-modified-windows/ ) to get Emacs+ESS (Emacs Speaks Statistics) installed.  
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

Assuming you have both R and Emacs installed, start Emacs and then type `M-x R` and hit Enter.
Boom, you have an R session running in Emacs.

## Opening, creating, and saving an R script

`C-x C-f` and type the path to a script and hit enter - remember you can use tab completion to avoid typing every letter.  
If you hit enter after only typing in a directory rather than a file, you can use the arrow keys and Enter to navigate to a file in the built-in file browser.  

If the filename you've entered doesn't exist, Emacs will create a 'buffer', which only when saved will write to the specified location.

Any file, already existing or a buffer currently being worked on, with the extension `.R` or `.r` will be treated as an R script, with syntax highlighting, and the ability to submit code directly to an R process.

`C-x C-s` will save/overwrite the file refrenced by the active window.

## Opening multiple windows

Now, you almost certainly don't want everything in 1 window and have to keep switching back and forth. Luckily you don't have to:  
`C-x 3` will split vertically  
`C-x 2` will split horizontally  
`C-x 1` will return to one window  
`C-x 0` will delete the current split you're working in  

Resizing horizontal splits is obvious, grab that divider and drag away. Not so much vertical splits. There's a tiny, not at all obvious, grey dividing line at the bottom of the total Emacs window which you can use to resize. See the image below.

![Alt](/window_resizing.gif "Creating and resizing windows")


## Switching between windows and buffers

`C-x o` (that's oh, not zero) will cycle through the windows you currently have open.  
If you want to change which 'buffer', or content, is shown in the current window, `C-LEFT` (LEFT = left arrow key) and `C-RIGHT` (RIGHT = right arrow key) will cycle through what you have open. You can have multiple views of the same content open in any window if you so desire. This can be handy if you want to see the header and footer of the same file at the same time, for instance.

## Typing, copying and pasting

You're not going to get very far without copying and pasting from <strike>Stackoverflow</strike> your previous work. So, at the basics:

`M-w` = copy  
`C-w` = cut  
`C-y` = paste (yank)  

If you stuff up:

`C-x u` = undo

## Running code

### At the prompt
If you're in the \*R\* window, just use R like you normally would. Type at the prompt and hit enter to evaluate code.

If you want to re-run or edit previously entered code:  
`M-p` = cycle backwards to *previous* submissions  
`M-n` = cycle forward to *next* submissions  

Something a little different is the ability to directly move your cursor to previously submitted code, and edit/interact with it like a text file.
This means you can also edit a previous line/code-chunk and resubmit. Handy if you've made a silly error that needs correcting.

![Alt](/04-correct.gif "Correcting a line above")

`TAB` completion still works like it does in any other R instance.

### In an .R script

There are [many shortcuts](https://ess.r-project.org/Manual/ess.html#Evaluating-code) for executing lines, paragraphs, functions, etc from a script. But in the short-term, there is one shortcut to rule them all:  
Highlight the code you want to run and `C-c C-c`

`C-M-i` will start tab completion, completing the text if there is only one possibility. If there are multiple possibilities, a new window will open listing all your choices from currently loaded packages.

## Getting help, aka RTFM

The standard old `?function` will open the help file as requested, typically within a new window in Emacs. E.g. `?table` for help on the base R `table` function. 
You can also use `C-c C-v` while at the R prompt, which will prompt you to start entering the function you would like to read the documentation for.  

As an added bonus, since an R help file is recognised as having R code in it, you can skip to the examples and have them run in your R session.

![Alt](/running_help.gif "Running help file scripts")


## Find and replace

`C-s` kicks off I-search, after which you can type some text. Emacs will jump to the first instance.  
Repeating `C-s` will jump to the next instance.

`M-%` (that's `M-shift-5`) will act somewhat like a typical find-and-replace you're used to.
- Specify the find text
- Specify the replace text
- Then `!` does a global replacement, `y` replaces the first instance and skips to the next, `n` doesn't replace the first instance and skips to the next

`M-C-%` (that's `M-C-shift-5`) is identical to the above, but with regex-based replacement. I'm not even going to try to explain regex if you're not familiar. Be aware that Emacs regex may not have every feature in your favourite implementation, see https://www.emacswiki.org/emacs/RegularExpression for full details

## Plotting

By default, any `plot` will open in an entirely new window external to Emacs, as it would if you were using R through a terminal.  
I'm a fan of this, because I like the possibility of multiple graphics devices and moving/resizing plots independently, as controlled by my window manager. Your mileage may vary on this.
