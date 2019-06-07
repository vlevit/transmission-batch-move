Description
===========

Simple shell script to rename all Transmission destination paths at once (by
editing Transmission's resume files).

Usage
=====

    transmission-batch-move [OPTIONS] PATTERN REPLACEMENT

The script will search PATTERN (regex) and replace it with REPLACEMENT
in all destination or incomplete-dir properties of Transmission resume
files in `~/.config/transmission/resume` directory. It will recalculate
lengths of new paths, so resume files should not break. All original
resume files are backed up. To be on the safe side make a backup before
running the script yourself.

Options
=======

 -h, --help           Displays this help.
 -y, --yes            Ignore safety prompt.
 -d, --destination    Change destination location.
 -i, --incomplete-dir Change incomplete directory location.
 --path=PATH          Specify configuration folder where resume directory
                      is located. Default is "~/.config/transmission"

Transmission daemon on Debian / Ubuntu
======================================

For Debian and derivative distributions Transmission daemon
configuration directory is set to `/var/lib/transmission-daemon/info`
by default. So pass `--path` as follows:

    transmission-batch-move --path=/var/lib/transmission-daemon/info -i PATTERN REPLACEMENT
