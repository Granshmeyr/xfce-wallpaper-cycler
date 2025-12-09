# XFCE Wallpaper Cycler

- **Why does this exist?**
	- You want basic wallpaper cycling.
	- The built-in solution in XFCE does not work.
	- That's it.

Cycle through your wallpaper folder randomly. Every wallpaper is shown at most once per-cycle of the folder (shuffled). This is a one-shot script, so you can schedule it however you want. I recommend a systemd user script.

### Usage Guide

Run the script with the following required parameters:
- `--property`: The xfconf-query path corresponding to your monitor's background image path. For example, mine is  `"/backdrop/screen0/monitorDP-4/workspace0/last-image"`. Find it using `xfconf-query --channel xfce4-desktop --list` and trial-and-error.

- `--wallpaper-folder`: The path containing your background image files.

Note that even if you change the wallpaper folder or add new images, the randomness won't mess up because the script only cares about images it knows it selected before. After all images that are available in the folder have been chosen, every file once again becomes capable of being chosen.
