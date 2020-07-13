# wolvirt

Wolvirt is a script to start Virtual Machines from Wake On Lan calls.

## Description

Install wolvirt if you are required to start virtual machines remotely. It captures
wake on lan packets, then searches the installed virtual machines and it starts
them if there is a match.

## Requirements

It needs libvirt installed and running in the server. So far only KVM virtual
machines have been tested. It runs on Perl and it requires some networking
and virt libraries installed.

## Required Libraries

### Debian / Ubuntu / Mint and derivatives

No all the required packages are available as debian package, so we must
install some from *cpanminus*

    $ sudo apt install libnet-pcap-perl libxml-libxml-perl libsys-virt-perl
    $ sudo apt install cpanminus
    $ sudo cpanm Net::PcapUtils

### RedHat and RPM like

    $ sudo dnf install 'perl(Net::Pcap)'
    $ sudo dnf install 'perl(Net::PcapUtils)'
    $ sudo dnf install 'perl(Sys::Virt)'
    $ sudo dnf install 'perl(XML::LibXML)'

If there is some package that can't be installed from *dnf* do it with *cpanminus*:

    $ sudo dnf install cpanminus
    $ sudo cpanm Net::PcapUtils

### Other OS

Install first cpanminus and then run:

    $ sudo cpanm Net::Pcap
    $ sudo cpanm Net::PcapUtils
    $ sudo cpanm Sys::Virt
    $ sudo cpanm XML::LibXML

Please report if you have success or problems in this stage.

## Installation

Install the required libraries as stated before. Then fetch *wolvirt* sources and install it
from there:

    $ git clone https://github.com/frankiejol/wolvirt.git
    $ cd wolvirt
    $ sudo install wolvirt /usr/local/bin/

## Run

There is no systemd init file yet, so you have to run it from the command line.
I will make this step easier if there is someone interested.

    $ sudo /usr/local/bin/wolvirt &

# Support

I am glad you are using wolvirt, I hope it fits your needs.
Open an issue if you need any feature or support. https://github.com/frankiejol/wolvirt/issues
