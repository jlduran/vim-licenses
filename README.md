vim-licenses
============

[Vim Plugin][] that Provides Commands to Add Licenses at the Top of the Buffer

[Vim Plugin]: http://www.vim.org/scripts/script.php?script_id=4871

Description
-----------

This plugin provides commands to insert licenses at the top of the buffer.
If the license is already at the top of the buffer, nothing is added.
This plugin works for the most popular programming languages, including
C, Java, Objective-C, C++, C#, PHP, Python, JavaScript, Ruby, Perl, Asm and Haskell.
The HTML and CSS languages are also supported.
It may work for other languages.

There are currently more than 10 licenses, and you can add your own.
To do so, copy the license text in ~/.vim/licenses/licenseFile.txt.
Then add a command for this license:

```vim
command! License call InsertLicense('licenseFile')
```

If your license file contains a `<year>` tag, it will be automatically
replaced by the current year.

The `<name of copyright holder>` tag will be automatically replaced by the
content of the `g:licenses_copyright_holders_name` variable (if not empty), so that
the copyright holder's name will be automatically added to the license.
Thus, you may want to add such a line to you .vimrc:

```vim
let g:licenses_copyright_holders_name = 'First Name Last Name <(login)@FreeBSD.org>'
```

And the `<name of author>` tag will be automatically replaced by the the
content of the `g:licenses_authors_name` variable (if not empty), so that
your name will be automatically added to the license.
Thus, you may want to add such a line to you .vimrc:

```vim
let g:licenses_authors_name = 'First Name Last Name <(login)@FreeBSD.org>'
```

If you do not want this plugin to create all these commands, you may
restrict to the licenses you want by using the `g:licenses_default_commands`
option. For instance, to have this plugin add only a command for the
BSD 2-Clause, BSD 3-Clause, ISC, MIT and Foobar licenses, use this:

```vim
let g:licenses_default_commands = ['bsd2', 'bsd3', 'isc', 'mit', 'foobar']
```

Commands
--------

`:Affero`
    Add the GNU Affero license to the buffer.

`:Allpermissive`
    Add the GNU All-Permissive license to the buffer.

`:Apache`
    Add the Apache License 2.0 to the buffer.

`:Boost`
    Add the Boost software license 1.0 to the buffer.

`:Bsd2`
    Add the BSD 2-Clause ["FreeBSD" license](https://www.gnu.org/licenses/license-list.html#FreeBSD) to the buffer.

`:Bsd3`
    Add the BSD 3-Clause ["Modified BSD" license](https://www.gnu.org/licenses/license-list.html#ModifiedBSD) to the buffer.

`:Cc0`
    Add the Creative Commons Zero license to the buffer.

`:Ccby`
    Add the Creative Commons Attribution 4.0 International License to the buffer.

`:Ccbysa`
    Add the Creative Commons Attribution-ShareAlike 4.0 International License to
    the buffer.

`:Cecill`
    Add the CeCILL license to the buffer.

`:Epl`
    Add the Eclipse Public License to the buffer.

`:Gfdl`
    Add the GNU Free Documentation License (FDL) to the buffer.

`:Gpl`
    Add the GNU General Public License (GPL) version 3.0 to the buffer.

`:Gplv2`
    Add the GNU General Public License (GPL) version 2.0 to the buffer.

`:Isc`
    Add the ISC license to the buffer.

`:Lgpl`
    Add the GNU "Lesser" General Public License (LGPL) license to the buffer.

`:Mit`
    Add the MIT license to the buffer.

`:Mitapache`
    Add the MIT/Apache Licence 2.0 dual license to the buffer.

`:Mpl`
    Add the Mozilla Public License 2.0 to the buffer.

`:Uiuc`
    Add the University of Illinois/NCSA Open Source License (UIUC) to the buffer.

`:Unlicense`
    Add the Unlicense to the buffer.

`:Verbatim`
    Add the GNU Verbatim Copying License to the buffer.

`:Wtfpl`
    Add the Do What The Fuck You Want To Public License (WTFPL) to the buffer.

`:Zlib`
    Add the Zlib License to the buffer.

Settings
--------

### `g:licenses_authors_name option`

The name of author to automatically insert in the buffer in the licence.

```vim
let g:licenses_authors_name = 'First Name Last Name <(login)@FreeBSD.org>'
```

### `g:licenses_default_commands`

Choose what commands to create for the listed licenses

```vim
let g:licenses_default_commands = ['bsd2', 'bsd3', 'isc', 'mit', 'foobar']
```

By default, only `:Bsd2`, `:Bsd3`, `:Isc`, and `:Mit` commands are available.
`:Foobar` is also created for `licenses/foobar.txt`.
