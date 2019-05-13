# clipboard-files
Cut, copy and paste files from the clipboard in a Linux terminal.

## Description
Clipboard-files provides command line operations to copy and paste files from the desktop environment clipboard in the terminal. Files and folders can be copied and moved to and from file manager applications, as well as between terminal instances.

The usage commands: `ccopy`, `ccut`, `cpaste`, `cshow` and `cclear` are symbolic links to the main script named `clipboard-files` in order to have short and concise command names.

## Usage

- `ccut FILE [FILE]...` Cut files or folders to clipboard
- `ccopy FILE [FILE]...` Copy files or folders to clipboard
- `cpaste` Paste from clipboard to current dir
- `cshow` Show files on the clipboard
- `cclear` Clear clipboard
- `clipboard-files` Show help

## Limitations

The script may not work in all desktop environments. The following should be supported:

- Gnome
- Mate
- Unity
- XFCE

## Installation

The following commands installs the script in `/usr/bin` and creates the usage command symlinks. 

Go to a tempory folder and run:

```text
git clone https://github.com/larspontoppidan/clipboard-files.git
sudo cp clipboard-files /usr/bin/
cd /usr/bin
sudo ln -s clipboard-files ccopy
sudo ln -s clipboard-files ccut"
sudo ln -s clipboard-files cpaste
sudo ln -s clipboard-files cshow
sudo ln -s clipboard-files cclear
```

The script requires `xclip`. Install it with:

```text
sudo apt install xclip
```
