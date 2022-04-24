# clipboard-files
Cut, copy and paste files from the clipboard in a Linux terminal.

## Description
Clipboard-files provides a series of command line operations to cut, copy and paste files from the desktop environment clipboard with a Linux terminal. Files and folders can be copied and moved, to and from file manager applications, as well as between terminal instances.

The usage commands: `ccopy`, `ccut`, `cpaste`, `cshow` and `cclear` are symbolic links to the main script named `clipboard-files` in order to have short and concise command names.

Read a little blog post about the script here: https://larsee.com/blog/2019/05/clipboard-files/

## Usage

- `ccut FILE [FILE]...` Cut files or folders to clipboard
- `ccopy FILE [FILE]...` Copy files or folders to clipboard
- `cpaste` Paste from clipboard to the current dir
- `cshow` Show files on clipboard
- `cclear` Clear clipboard without any file operations
- `. ccd` cd to the dir of the 1st file on clipboard
- `clipboard-files` Show help

## Example

```text
$ ccopy file1.txt file2.jpg
2 item(s) copied to clipboard
$ cshow
Operation: copy
/home/lars/temp/file1.txt
/home/lars/temp/file2.jpg
$ cd folder/
$ cpaste
Copying the following items(s) to current dir:
/home/lars/temp/file1.txt
/home/lars/temp/file2.jpg
$ ccut *
2 item(s) cut to clipboard
$ cd ..
$ cpaste
Moving the following items(s) to current dir:
/home/lars/temp/folder/file1.txt
/home/lars/temp/folder/file2.jpg
```

## Limitations

The script may not work in all desktop environments. The following should be supported:

- Gnome
- Mate
- Unity
- XFCE
- KDE Plasma (ccut not supported)

## Installation

The script requires `xclip`. Install from a package repository, eg.:

```text
sudo apt install xclip
```

### Non-KDE-Plasma install

The following commands will install the script in `/usr/bin/` and create the required command symlinks.

Go to a temporary folder and run:

```text
git clone https://github.com/larspontoppidan/clipboard-files.git
sudo cp clipboard-files/clipboard-files /usr/bin/
cd /usr/bin
sudo ln -s clipboard-files ccopy
sudo ln -s clipboard-files ccut
sudo ln -s clipboard-files cpaste
sudo ln -s clipboard-files cshow
sudo ln -s clipboard-files cclear
sudo ln -s clipboard-files ccd
```

### KDE-Plasma install

The following commands will install the script in `/usr/bin/` and create the required command symlinks.

```text
git clone https://github.com/larspontoppidan/clipboard-files.git
sudo cp clipboard-files/clipboard-files-kde-plasma /usr/bin/
cd /usr/bin
sudo ln -s clipboard-files-kde-plasma ccopy
sudo ln -s clipboard-files-kde-plasma cpaste
sudo ln -s clipboard-files-kde-plasma cshow
sudo ln -s clipboard-files-kde-plasma cclear
sudo ln -s clipboard-files-kde-plasma ccd
```

## Uninstallation

```text
cd /usr/bin
sudo rm clipboard-files ccopy cpaste cshow cclear ccd ccut
```

To remove `xclip`:
```text
sudo apt purge xclip
```

## Thanks to

- The user `woodenshoe-wi` in this thread: http://murga-linux.com/puppy/viewtopic.php?t=111880&start=15 for writing the original clipboard interfacing code
