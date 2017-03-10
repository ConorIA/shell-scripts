# autotype4pass
A simple Linux script to auto-type usernames and passwords stored in [Pass](https://www.passwordstore.org/). 

# Requires
- [Pass](https://www.passwordstore.org/)
- [xdotool](http://www.semicomplete.com/projects/xdotool)
- [xclip](https://github.com/astrand/xclip)

# Installation
- Save the script somewhere accessible
- Mark the script as executable (via gui or "chmod +x")
- Assign a keyboard shortcut (like "Ctrl + Alt + a") the launch the script. 

# Usage
The script assumes that your passwords are organized by category and website name.
It also assumes that the usernames are prefixed by "login" and that urls are saved in the pass `.gpg` files.

To use the script, just place your mouse over the "username" field on a webpage and hit the key combination to launch the script. 
The script will invoke `pass find` to find an entry matching the window title of your web browser. 
If there are no matches, or too many matches, the script will search by url using `pass grep` (this is pretty slow).

I wrote this script after migrating to pass from Keepass. It is matched to my workflow, but I am happy to modify it to make it useful to others. 
