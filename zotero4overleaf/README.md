# zotero4overleaf
A simple linux script to auto-type [LaTeX](https://www.latex-project.org/)- or [pandoc](pandoc.org)-formatted citations from Zotero to the active program window. Originally, this script was written for use with [Overleaf](https://www.overleaf.com), but it will paste citations in any other active program or window. 

# Requires
- [Zotero](https://www.zotero.org/)
- [Better Bibtex](https://zotplus.github.io/better-bibtex/) _Note: Ensure that 'HTTP export' is enabled in preferences_
- [xdotool](http://www.semicomplete.com/projects/xdotool/)
- Zenity (sort of optional ... see note under "Usage")

# Installation
- Save the script somewhere accessible
- Mark the script as executable (via gui or "chmod +x")
- Assign a keyboard shortcut (like "Ctrl + Alt + z") the launch the script. 

# Now serving Markdown users! (revised 2016-07-21)
If you use LaTeX sometimes, and Markdown other times, you may benefit from some new options. You now choose a default citation type, either "latex" or "pandoc" when you first configure the script. If you need to change the citation type, simply call the script with the -t flag, and it will swap. The change will persist until you call the -t glag again. If you often switch between LaTeX and Mardown, I recommend adding another keyboard shortcut (e.g. "Shift + Ctrl + Alt + Z") to call the command with the -t option. 

# Usage
When you run the script, it will do a few things. First, it will check if Zotero with Better Bibtex is running. 
If the Better Bibtex probe checks out, the script will pull up the Zotero quickpick dialogue and xdotool will type the citation using the command of your choosing.

If Zotero with Better Bibtex is not running, this script should launch Zotero, wait a few (10) seconds, then do the above. 

If something weird happens, it will send you a notification. 

Note: This script now uses a Zenity dialogue to create a text file in the user's `$HOME/.config/` directory that contains the command needed to launch either Zotero standalone or Firefox with the Zotero add-on. You can skip this step by putting a file `$HOME/.config/.zotero4overleaf.conf` with the command you use to launch Zotero, the citation command to use in LaTeX, and the name of your preferred citation type. This is easily done on the command line by, for example:
```
echo "zotero" > ~/.zotero4overleaf.conf
echo "autocite" >> ~/.zotero4overleaf.conf 
echo "latex" >> ~/.zotero4overleaf.conf 
```

# Importing your Zotero bibliography into Overleaf

It should go without saying that you will need to import your Zotero references into Overleaf in order to cite them. Details here: https://www.overleaf.com/blog/174-import-your-bibs-reference-management-tools-now-linked-to-overleaf-number-backtoschool
