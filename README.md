|||||||||||||||||||||||||||
||||| Linux terminal ||||||
|||||||||||||||||||||||||||

1. List files and directories
	- ls

2. Change current directory
	- cd [directory name]

3. Create new directory
	- mkdir [new directory name]

4. Create empty file
	- touch [filename].[file format]

5. Remove delete empty directory
	- rmdir [filename]

6. Copies files or directory 
	- cp source [file/directory name]

7. Paste file or directory
	- change to directory where the file is - cd [directory]
	- copy and paste to directory - cp ~/file.txt ~/../Documents

	- Copy from documents directory to home - cp ~/Documents/file.txt ~/

8. Delete all files in a directory
	- rm ~/Documents/*

9. Delete all files and subdirectories
	- rm -r ~/Documents/*

10. Remove multiple files
	- rm /path/[filename] /path/[filename]

11. Mount a usb drive
  a. check usb drive = lsblk
  b. create new usb dir (option if no /mnt/usb yet) = sudo mkdir /mnt/usb
  c. mount usb = sudo mount /dev/usb /mnt/usb
  d. nav to usb dir = cd /mnt/usb
  e. check files = ls

12. Unmount usb
  a. back to home = cd
  b. unmount usb dir = sudo umount /mnt/usb
  c. eject usb (option if ready to remove from device) = sudo eject /dev/sda1

13. Copy and paste a file
  - cp file-to-copy.txt copied-file.txt
  - cp file-to-copy.txt ../Documents
  - cp file-to-copy.txt /Documents

14. Check what path i'm currently at
  - pwd

15. Utility
  Must install either of the following
  - htop
  - btop

16. Fuzzy Search
  Must install fzf
  - fzf

17. Easy navigation
  Adding code to bashrc to custom
  - s

18. Use Nautilus / Explorer in linux
  Must install nautilus
  - nautilus

19. Display distribution logo and cpu details
  must install fastfetch
  -fastfetch

20. Adjust brightness
   - brightnessctl set <value> or <value>%
   - brightnessctl -help

21. Use bluetooth
   - bluetoothctl
   - power on
   - scan on
   - pair <device id>
   - connect <device id>

22. Shortcut to this cheat-sheet
   - cs [enter]

23. Rename a directory
   - mv old_directory_name new_directory_name
   - If inside another directory - mv parent_directory/old_directory parent_directory/new_directory

24. Rename a file
   - mv old_file.txt new_file.txt

25. Screen shot
   * install guide https://dev.to/dianjuar/i3wm-screenshot-shortcuts-3n7b
   - ctrl + print
   - print
   - clipboard select - ctrl + shift + print

26. Edit photos 
   - use gimp

27. Open in live server
   - Install live-server
   1. navigate to project directory
   2. live-server
   3. check for the status

28. Multiple monitor
   - must install xrandr
   - check the connected devices using "xrandr"
   - xrandr --output HDMI-2 --auto --right-of eDP1
   - --output [name of connection]
   - --mode [resolution]
   - --right-of [left side screen]
   - --auto (use default)

29. Transfer a window to different active workspace
   - Open window that i want to transfer
   - [mod] + shift + workspace number

30. Zoom in terminal
   - ctrl + shift + "+"      

31. Zoom out terminal
   - ctrl + -

32. View all available emulator
   - emulator -list-avds

33. Open emulator
   - emulator -avd [avd_name]
   - emulator @[avd_name]

34. Control battery charging threshold
    - installation - sudo dnf install tlp tlp-rdw
    - configure threshold - sudo nvim /etc/tlp.conf
    - change the following values depending on the threshold I want
    START_CHARGE_THRESH_BAT0=90
    STOP_CHARGE_THRESH_BAT0=90
    - restart TLP to apply changes - sudo systemctl restart tlp
    - check in terminal if changes are applied - sudo tlp-stat -b

|||||||||||||||||||||||||||||||||||||||||||||||||||||
||||| Software shortcuts to open using terminal |||||
|||||||||||||||||||||||||||||||||||||||||||||||||||||

1. Google Chrome - google-chrome
2. Mozilla Firefox - firefox
3. Libre office - libreoffice
4. Visual studio code - code
5. Photo editor - gimp


||||||||||||||||||||||||||||||||
|||||||||  Docker ||||||||||||||
||||||||||||||||||||||||||||||||
GENERAL COMMANDS
1. Start the docker daemon
    - docker -d
2. Get help with Docker. Can also use –help on all subcommands
    - docker --help
3. Display system-wide information
    - docker info

IMAGES
1. List local images
    - docker images
2. Build an Image from a Dockerfile
    - docker build -t <image_name>
3. Build an Image from a Dockerfile without the cache
    - docker build -t <image_name> . –no-cache
4. Delete an Image
    - docker rmi <image_name>
5. Remove all unused images
    - docker image prune

CONTAINER
1. Create and run a container from an image, with a custom name:
    - docker run --name <container_name> <image_name>
2. Run a container with and publish a container’s port(s) to the host.
    - docker run -p <host_port>:<container_port> <image_name>
3. Run a container in the background
    - docker run -d <image_name>
4. Start or stop an existing container:
    - docker start|stop <container_name> (or <container-id>)
5. Remove a stopped container:
    - docker rm <container_name>
6. Open a shell inside a running container:
    - docker exec -it <container_name> sh
7. Fetch and follow the logs of a container:
    - docker logs -f <container_name>
8. To inspect a running container:
    - docker inspect <container_name> (or <container_id>)
9. To list currently running containers:
    - docker ps
10. List all docker containers (running and stopped):
    - docker ps --all
11. View resource usage stats
docker container stats

||||||||||||||||||||||||||||
|||||| Git commands ||||||||
||||||||||||||||||||||||||||

1. Initialize a new git repository  in the current directory
	- git init

2. Creates a copy of a remote repository in local
	- git clone [remote_repository_url]
3. Add changes to staging area
	- git add [filename]
	- add all changes - git add .

4. Records changes from staging area to repository
	- git commit -m "[commit message]"

5. Shows the status of changes as untracked, modified, or staged status
	- git status

6. Shows all commit records in the repository
	- git log

7. Fetch changes from remote repository to local branch
	- git pull

8. Upload current branch to remote branch
	- git push .

9. Upload new branch from local to remote
	- git push origin [branch_name]

10. List all branch in the repository
	- git branch

11. Switch between branches 
	- git checkout [branch_name]

12. Create new branch
	- git checkout -b [branch_name]

13. Merge branch to current branch
	- git merge [branch to combine]

14. Shows the difference between the working branch and last commit
	- git diff

15. Shows a list of remote repositories
	- git remote -v

16. Temporary saves the current working branch that is not ready to commit
	- git stash

17. Retrieve and drop stash
	- git stash pop

18. See all stash
	- git stash list

19. Remove all stage area
	- git reset 

20. Remove resent commit
	- git reset HEAD^

21. Delete git branch
   Only for merged branch
   - git branch -d <branch name>

   Force to delete without merging
   - git branch -D <branch name>

|||||||||||||||||
|||| VIM |||||||
||||||||||||||||

1. List buffers
    - :ls

2. Open buffer
    - :buffer <buffer number>
    - :buffer <filename>

3. Close buffer
    - open buffer -> :bd



|||||||||||||||||
||| NeoVim||||||
||||||||||||||||

## Navigation:

- `h`: Move left
- `j`: Move down
- `k`: Move up
- `l`: Move right

- `w`: Move to the beginning of the next word
- `e`: Move to the end of the current word
- `b`: Move to the beginning of the current word
- `G`: Move to the last line of the file
- `gg`: Move to the first line of the file

- `0`: Move to the beginning of the line
- `^`: Move to the first non-blank character of the line
- `$`: Move to the end of the line

- `Ctrl + u`: Move half a page up
- `Ctrl + d`: Move half a page down
- `Ctrl + e`: Scroll one line down
- `Ctrl + y`: Scroll one line up

## Editing:

- `i`: Enter insert mode before the cursor
- `I`: Enter insert mode at the beginning of the line
- `a`: Enter insert mode after the cursor
- `A`: Enter insert mode at the end of the line
- `o`: Open a new line below the current line and enter insert mode
- `O`: Open a new line above the current line and enter insert mode

- `Esc`: Exit insert mode

- `yy`: Copy (yank) a line
- `p`: Paste after the cursor
- `P`: Paste before the cursor

## Saving and Quitting:

- `:w`: Save changes

- `:q`: Quit (close the current file)
- `:wq` or `:x`: Save and quit
- `:q!`: Quit without saving changes
- `:wqa` or `:xa`: Save all and quit


## Searching:

- `/pattern`: Search forward for the specified pattern
- `?pattern`: Search backward for the specified pattern
- `n`: Move to the next occurrence
- `N`: Move to the previous occurrence

## Miscellaneous:

- `u`: Undo
- `Ctrl + r`: Redo

- `"+yy`: Copy to system clipboard (requires Neovim with clipboard support)
- `"+p`: Paste from system clipboard (requires Neovim with clipboard support)

## Open buffers
- <space> `fb`

## Open live grep
- <space> `fg`

## Open help
- <space> `fh`

## Open telescope
- <space> `fp`

## Folding rows
 1. press v
 2. select rows you want to hide - use shortcuts like %
 3. press zf

## Show hidden rows
 - za

## managing created folds
   - opening fold - zo
   - closing fold - zc

## Changing multiple text
   change all
   - :%s/text/changedText/g
   change selected text
   - select the items using v
   -:s/text/changedText/g

## Removing buffers
   - :bd <buffer number of name>

## Jump to next }])
   - navigate to {[ and press %

||||||||||||||||||||||||||||
|||||||  netrw listing |||||
||||||||||||||||||||||||||||

## create new file
   - shift + %

## create new directory
   - d

## Splitting window
   - :vsplit
   - ctrl + w + h

## Adding horizontal window inside a window
   - ctrl + w + s

## Changing between window
   - ctrl + w + w

## Vertical resizing window (From splits)
   - select window - ctrl + w + w 
   - :vertical resize 40

## Horizontal resizing window (From splits)
   - :horizontal resize 40

## Closing splits
    - select window to close
    - :q

||||||||||||||||||||||||||||
||||||||| tmux |||||||||||||
||||||||||||||||||||||||||||


//////Session//////
//Note: all "b" character are configured to "s". b as the default

1. Start tmux
  - tmux
  - ctrl + b ":new"

2. Detach tmux
  - ctrl + d

3. List existing tmux session
  - tmux list-sessions
  - tmux ls
  - ctrl + b s
  - edited to ctrl + s s

4. Create new tmux session with name
  - tmux new-session -s [session name]
  - ctrl + b ":new -s [session name]

5. Exit tmux
  - exit

6. Start new session
  - tmux new -s [session name]

7. Kill/delete session
  - tmux kill-ses -t [session name]

8. Attach to session
  - tmux a -t [session name]

9. Attach to last session
  - tmux a

10. Kill delete current session
  - tmux kill-session -a

11. Rename a session
   - ctrl + b + $

12. Rename a window
   - ctrl + b + ,

13. Move to next session
   - ctrl + b + )

14. Move to previous session
   - ctrl + b + (

15. Adding horizontal pane
   - ctrl + b %

16. Kill current window
   - ctrl + b + &
   - answer y/yes


//////Window//////
customized "b" to "s"
11. Create new window
  - ctrl + b c

12. Display windows
  - ctrl + b w

13. Close current window
  - ctrl + b &
  

14. Rename current window 
  - ctrl + b ,

////// Panes //////

15. Add new pane on the right
  - ctrl + b %

16. Add new pane on the bottom
  - ctrl + b "

17. Adjusting pane size
  Right - [hold]ctrl + b + right arrow
  Left - [hold]ctrl + b + left arrow
  Up - [hold]ctrl + b + up arrow
  Down - [hold]ctrl + b + down arrow

18. Switching between panes
  Right - ctrl + b + right arrow
  Left - ctrl + b + left arrow
  Up - ctrl + b + up arrow
  Down - ctrl + b + down arrow




||||||||||||||||||||
||||| Flutter ||||||
||||||||||||||||||||

## Flutter create new application
- flutter create <app name>


## Flutter path
- export PATH="$PATH:`pwd`/flutter/bin"
