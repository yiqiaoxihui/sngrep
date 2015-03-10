# sngrep [![Build Status](https://travis-ci.org/irontec/sngrep.svg)](https://travis-ci.org/irontec/sngrep)

sngrep is a tool for displaying SIP calls message flows from terminal.

It supports live capture to display realtime SIP packets and can also be used
as PCAP viewer.

[Some screenshots of sngrep](https://github.com/irontec/sngrep/wiki/Screenshots)

## Installing

### Binaries
#### Debian / Ubuntu
[Install sngrep Debian/Ubuntu package](https://github.com/irontec/sngrep/wiki/Installing-Binaries#debian--ubuntu)

#### CentOS / RedHat / Fedora
[Install sngrep CentOS/RedHat/Fedora package](https://github.com/irontec/sngrep/wiki/Installing-Binaries#centos--fedora--rhel)

#### OSX
OSX users can install sngrep using [homebrew](https://github.com/Homebrew/homebrew)

    brew install sngrep

### Building from sources
Prerequisites

 - libncurse5 - for UI, windows, panels.
 - libpcap - for capturing packets.
 - libssl - (optional) for TLS transport decrypt
 - libncursesw5 - (optional) for UI, windows, panels (wide-character support)
 - libpcre - (optional) for Perl Compatible regular expressions

On most systems the commands to build will be the standard autotools procedure:

    ./bootstrap.sh
	./configure
	make
	make install (as root)

You can pass following flags to ./configure to enable some features

| configure flag | Feature |
| ------------- | ------------- |
| `--with-openssl` | Adds OpenSSL support to parse TLS captured messages (req. libssl)  |
| `--with-pcre`|  Adds Perl Compatible regular expressions support in regexp fields |
| `--enable-unicode`   | Adds Ncurses UTF-8/Unicode support (req. libncursesw5) |

You can find [detailed instructions for some distributions] (https://github.com/irontec/sngrep/wiki/Building) on wiki.

## Usage

See `--help` for a list of available flags and their syntax

For example, sngrep can be used to view SIP packets from a pcap file, also applying filters

    sngrep -I file.pcap host 192.168.1.1 and port 5060

or live capturing, saving packets to a new file

	sngrep -d eth0 -O save.pcap port 5060 and udp



You can configure some options using `sngreprc` file

## Frequent Asked Questions
See FAQ on [Github Wiki](https://github.com/irontec/sngrep/wiki#frequent-asked-questions)

## License 
    sngrep - SIP Messages flow viewer
    Copyright (C) 2013,2014 Irontec S.L.

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    In addition, as a special exception, the copyright holders give
    permission to link the code of portions of this program with the
    OpenSSL library under certain conditions as described in each
    individual source file, and distribute linked combinations
    including the two.
    You must obey the GNU General Public License in all respects
    for all of the code used other than OpenSSL.  If you modify
    file(s) with this exception, you may extend this exception to your
    version of the file(s), but you are not obligated to do so.  If you
    do not wish to do so, delete this exception statement from your
    version.  If you delete this exception statement from all source
    files in the program, then also delete it here.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

