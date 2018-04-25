# PathLocate

## Overview

PathLocate is a small command line utility that allows you to quickly search for files located in directories listed in the `PATH` environment variable.

The program allows you to enter many names/masks of files on one command line, limit the number of returned files, ignore or take into account the size of characters, calculate CRC32 checksums, SHA-1 and SHA-2 hashes, display the last modification time of files, their size, VersionInfo block from executable files (on Windows) and other.

## Download

Source: https://github.com/jackdp/PathLocate

Binary (Windows 32-bit, Windows 64-bit, Linux 32-bit, Linux 64-bit): http://www.pazera-software.com/products/path-locate/

## Documentation

Full documentation available at http://www.pazera-software.com/products/path-locate/help.html

## Compilation

> Build and tested on CodeTyphon 6.40 with FPC 3.1.1

To compile, you need:
- [CodeTyphon Programming Studio](http://pilotlogic.com/sitejoom/). After small modifications, the program can also be compiled in the [Lazarus IDE](https://www.lazarus-ide.org/).
- [JPL.CmdLineParser](https://github.com/jackdp/JPL.CmdLineParser) unit.
- A several Pascal units from my library [JPLib](https://github.com/jackdp/JPLib/).
- Mini-FPC [MFPC](https://github.com/jackdp/MFPC).
- Wolfgang Ehrhardt's [hashing units](http://www.wolfgang-ehrhardt.de/crchash_en.html) (all files in the [src/we](src/we) directory).

How to build:
1. Open `src\PathLocate.ctpr` file with CodeTyphon.
1. Set build mode for your destination system.  
Select menu `Project -> Project Options...` A new window will appear.
In the tree view (on the left), select `Compiler Options`.
At the top of this window you can select the build mode from the dropdown list.
Choose: `Release Win32`, `Release Win64`, `Release Lin32` or `Release Lin64`.
3. Build project (menu `Run->Build`).

## Changelog / Releases

**Version 1.1** (2018.03.19)  
- Compilation in a new version of the CodeTyphon (6.40).
- [+] Calculation of MD5, SHA-1 and SHA-2-256 checksums. Switches: `--md5` `--sha1` `--sha2`
- [+] Highlighting of executable files: EXE, DLL, BAT, CMD, BPL (on Windows), and SH, SO (on Linux). Switches: `-he` `-hd` `-hb` `-hc` `-hp` `-hs` `-hl`
- [+] Highlighting the text provided by the user. Switches: `-hus` `-hus2`
- [+] Sorting. Switches: `-sb` `-sd`
- [+] Displaying the list of directories specified in the **PATH** environment variable. Switch `-ld`
- [+] Long format switch: `--long`.
- [+] The user can define the text used to separate categories of information. Switches: `-sl` `-sdt`.
- [+] Displaying more detailed information about errors. Switch `-err`
- [+] Displaying the creation (Windows only), last write and last access time of found files. Switches: `-dc` `-dw` `-da`
- [+] The ability to display file attributes on Windows system. Switch: -a
- [+] Displaying the short version info (and nothing more). It can be useful for detecting the PathLocate version from batch files. Switch `-vs`
- [+] [Linux] Detecting if the output is a character device (terminal, printer). If so, the PathLocate will use ANSI escape codes to display colors. If not, ANSI codes will not be generated by the program. As a result, the output data stream can be redirected to a file/pipe, and it will not be "cluttered" with unnecessary data.

**Version 1.0** (2018.01.25)  
Initial release.

## Note

This program was made for my private use, but it may also be useful to someone.

PathLocate can be useful for administrators to quickly locate executable files, check their version, as well as in batch files for making decisions in the absence of any files necessary for the proper operation of the script.
