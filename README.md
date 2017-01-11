Description
===========

Simple shell script to rename all Transmission destination paths at once (by
editing Transmission's resume files).

Usage
=====

    transmission-batch-move [OPTIONS] PATTERN REPLACEMENT

The script will search PATTERN (regex) and replace it with REPLACEMENT
in all destination properties of Transmission resume files in
`~/.config/transmission/resume` directory. It will recalculate lengths
of new destination paths, so resume files should not break. All
original resume files are backed up. To be on the safe side make a
backup before running the script yourself.

Options
=======

     -h, --help    Displays this help.
     -y, --yes     Ignore safety prompt.
     --path=PATH   Specify configuration directory where resume folder
                   is located. Default is "~/.config/transmission"

Transmission daemon on Debian / Ubuntu
======================================

For Debin and derivative distributions Transmission daemon
configuration directory is set to `/var/lib/transmission-daemon/info`
by default. So pass `--path=transmission-batch-move` as follows:

    transmission-batch-move --path=/var/lib/transmission-daemon/info PATTERN REPLACEMENT
