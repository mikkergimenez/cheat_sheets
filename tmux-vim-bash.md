## VIM

### Line Navigation

k – navigate upwards
j – navigate downwards
l – navigate right side
h – navigate left side

By using the repeat factor in VIM we can do this operation for N times. For example, when you want to
go down by 10 lines, then type “10j”.

### Within Line Navigation 

0 – go to the starting of the current line.
^ – go to the first non blank character of the line.
$ – go to the end of the current line.
g_ – go to the last non blank character of the line.

### Vim Screen Navigation

H – Go to the first line of current screen.
M – Go to the middle line of current screen.
L – Go to the last line of current screen.
ctrl+f – Jump forward one full screen.
ctrl+b – Jump backwards one full screen
ctrl+d – Jump forward (down) a half screen
ctrl+u – Jump back (up) one half screen

### Vim Special Navigation

N% – Go to the Nth percentage line of the file.
NG – Go to the Nth line of the file.
G – Go to the end of the file.
`” – Go to the position where you were in NORMAL MODE while last closing the file.
`^ – Go to the position where you were in INSERT MODE while last closing the file.
g – Go to the beginning of the file.

### Vim Word Navigation
e – go to the end of the current word.
E – go to the end of the current WORD.
b – go to the previous (before) word.
B – go to the previous (before) WORD.
w – go to the next word.
W – go to the next WORD.

WORD – WORD consists of a sequence of non-blank characters, separated with white space.
word – word consists of a sequence of letters, digits and underscores.

Example to show the difference between WORD and word

192.168.1.1 – single WORD
192.168.1.1 – seven words.

### Vim Paragraph Navigation
{ – Go to the beginning of the current paragraph. By pressing { again and again move to the previous paragraph beginnings.
} – Go to the end of the current paragraph. By pressing } again and again move to the next paragraph end, and again.

### Vim Search Navigation
/i – Search for a pattern which will you take you to the next occurrence of it.
?i – Search for a pattern which will you take you to the previous occurrence of it.
* – Go to the next occurrence of the current word under the cursor.
# – Go to the previous occurrence of the current word under the cursor.
7. Vim Code Navigation
% – Go to the matching braces, or parenthesis inside code.

### Vim Navigation from Command Line
Vim +N filename: Go to the Nth line of the file after opening it.

vim +10 /etc/passwd

Vim +/pattern filename: Go to the particular pattern’s line inside the file, first occurrence from first. In the following example, it will open the README file and jump to the first occurrence of the word “install”.

vim +/install README

Vim +?patten filename: Go to the particular pattern’s line inside the file, first occurrence from last. In the following example, it will open the README file and jump to the last occurrence of the word “bug”.

vim +?bug README


## BASH

Ctrl+A - go to the beginning of a line
Ctrl+E- go to the end of a line
Ctrl+K - clears line up to the cursor
Ctrl+W - delete last word
Ctrl+L - clear the screen (equivalent of the clear command)

## TMUX

Create New Session: ```$ tmux new -s session-name```

Detaching from a session
You want a pause between the shortcut and the following command.
To detach from a session you invoke the shortcut (ctrl-b)—followed by d, for detatch, or by typing detach explicitly.

Related
Summary: Algorithms to Live By
$ ctrl–b–d

$ tmux detach

Consider remapping CAPSLOCK to CONTROL in your OS to make this easier.
Show existing sessions
You can—and often will—have multiple tmux sessions on a single system, so you want to be able to see what they are.

You can also show sessions using the shortcut ctrl–b–s.
$ tmux ls


A VIEW OF RUNNING SESSIONS

Attaching to an existing session
Now that we can see those sessions, you can either connect to one by session name, or by number.

The UL Newsletter: Finding the Patterns in the Noise…
Get a weekly analysis of what's happening in security and tech—and why it matters.
YOUR BEST EMAIL
The session names start at 0 and increment upwards.
$ tmux attach -t 0

tmux a will connect you to the first available session.
$ tmux attach -t session-name

Killing a session
There are times when you’ll want to destroy a session outright, and that can be done similar to attaching to one.

$ tmux kill-session -t session-name

You can also kill tmux altogether with killall tmux.
Windows and Panes
tmuxnesting

Related
The Unsupervised Learning Daily Routine
I don’t use this functionality myself.
Another feature of tmux is the ability to break your session into more discreet components, called windows and panes. These are good for organizing multiple activities in a logical way.

Basically, tmux sessions have windows, and windows have panes. Here’s how I conceptualize the structure.

Sessions are for an overall theme, such as work, or experimentation, or sysadmin.
Windows are for projects within that theme. So perhaps within your experimentation session you have a window titled noderestapi, and one titled lua sample.
Panes are for views within your current project. So within your sysadmin session, which has a logs window, you may have a few panes for access logs, error logs, and system logs.
A Quick Command Reference
These all play off of the ctrl-b shortcut.

Basics
? get help
Session management
s list sessions
$ rename the current session
d detach from the current session
Windows
c create a new window
, rename the current window
w list windows
% split horizontally
" split vertically
n change to the next window
p change to the previous window
0 to 9 select windows 0 through 9
Panes
% create a horizontal pane
" create a vertical pane
h move to the left pane. *
j move to the pane below *
l move to the right pane *
k move to the pane above *
q show pane numbers
o toggle between panes
} swap with next pane
{ swap with previous pane
! break the pane out of the window
x kill the current pane
