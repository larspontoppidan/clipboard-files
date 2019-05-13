# clipboard-files
Cut, copy and paste files from clipboard in the Linux terminal.

## Description
Installing clipboard-files allows you to copy and paste files from the desktop environment clipboard in the terminal. Copying and pasting files is possible between terminal instances as well as between various file manager applications and the terminal.

The usage commands: `ccopy`, `ccut`, `cpaste`, `cshow` and `cclear`are symbolic links to the main script named `clipboard-files`.

## Usage

- `ccut FILE... ` Cut files or folders to clipboard
- `ccopy FILE... ` Copy files or folders to clipboard
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

The script requires `xclip`. Install with:
```text
sudo apt install xclip
```

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
