# clipboard-files
Cut, copy and paste files from the clipboard in a Linux terminal.

Updated to support Wayland.

## Description
Clipboard-files provides a series of command line operations to cut, copy and paste files from the desktop environment clipboard with a Linux terminal. Files and folders can be copied and moved, to and from file manager applications, as well as between terminal instances.

The usage commands: `ccopy`, `ccut`, `cpaste`, `cshow` and `cclear` are symbolic links to the main script named `clipboard-files` in order to have short and concise command names.

Read more about the script here: https://larsee.com/blog/2019/05/clipboard-files/

## Usage

- `ccut FILE [FILE]...` Cut files or folders to clipboard (may not be supported)
- `ccopy FILE [FILE]...` Copy files or folders to clipboard
- `cpaste [DIR]` Paste files from clipboard into DIR or current dir
- `cshow` Show files on clipboard
- `cclear` Clear clipboard without any file operations
- `. ccd` cd to the dir of the 1st file on clipboard
- `clipboard-files-wayland` / `clipboard-files-kde` / `clipboard-files` Show help

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

The script may not work with all desktop environments and ccut may not be available.

There are three script versions:

- `clipboard-files-wayland` Intended for Wayland environments and has been tested with KDE Plasma 6. ccut is not supported.
- `clipboard-files-kde` Intended for X11 KDE. ccut is not supported.
- `clipboard-files` Intended for non-KDE X11 environments.


## Installation steps for Wayland

The script requires `wl-clipboard`. Install from a package repository, eg.:

```text
sudo apt install wl-clipboard
```

The following commands will install the script in `/usr/bin/` and create the required command symlinks.

Cd to a temporary folder and run:

```text
git clone https://github.com/larspontoppidan/clipboard-files.git
sudo cp clipboard-files/clipboard-files-wayland /usr/bin/
cd /usr/bin
sudo ln -s clipboard-files-wayland ccopy
sudo ln -s clipboard-files-wayland cpaste
sudo ln -s clipboard-files-wayland cshow
sudo ln -s clipboard-files-wayland cclear
sudo ln -s clipboard-files-wayland ccd
```

### Uninstall steps

```text
cd /usr/bin
sudo rm clipboard-files-wayland ccopy cpaste cshow cclear ccd
```

To remove `wl-clipboard`:
```text
sudo apt purge wl-clipboard
```

## Installation steps for X11 KDE

The script requires `xclip`. Install from a package repository, eg.:

```text
sudo apt install xclip
```

The following commands will install the script in `/usr/bin/` and create the required command symlinks.

Cd to a temporary folder and run:

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

### Uninstall steps

```text
cd /usr/bin
sudo rm clipboard-files-kde-plasma ccopy cpaste cshow cclear ccd
```

To remove `xclip`:
```text
sudo apt purge xclip
```

## Installation steps for X11 non-KDE

The following commands will install the script in `/usr/bin/` and create the required command symlinks.

Cd to a temporary folder and run:

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

### Uninstall steps

```text
cd /usr/bin
sudo rm clipboard-files ccopy ccut cpaste cshow cclear ccd
```

To remove `xclip`:
```text
sudo apt purge xclip
```

## Thanks to

- The user `woodenshoe-wi` in this thread: http://murga-linux.com/puppy/viewtopic.php?t=111880&start=15 for writing the original clipboard interfacing code that inspired this project.
