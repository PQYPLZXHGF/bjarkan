# bjarkan

[![Snap Status](https://build.snapcraft.io/badge/willdeberry/bjarkan.svg)](https://build.snapcraft.io/user/willdeberry/bjarkan)
[![PyPI version](https://badge.fury.io/py/bjarkan.svg)](https://badge.fury.io/py/bjarkan)
[![PyPI](https://img.shields.io/pypi/pyversions/bjarkan.svg)](https://pypi.python.org/pypi/bjarkan)
[![License](http://img.shields.io/:license-bsd-blue.svg)](https://github.com/willdeberry/bjarkan/blob/master/LICENSE)

A bluez 5 compatible command line utility

* [License](#license)
* [Installation](#installation)
    * [Requirements](#requirements)
    * [Pip](#pip)
    * [Manual](#manual)
* [Usage](#usage)
    * [Pairing/Connecting](#pairingconnecting)
    * [Unpair](#unpair)
    * [Connect](#connect)
    * [Disconnect](#disconnect)
    * [Paired-devices](#paired-devices)
    * [Connected-devices](#connected-devices)

## License
Copyright (c) 2016, GetWellNetwork, Inc.
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## Installation

### Snap Package
```
sudo snap install bjarkan
```

### Pip
```
sudo apt-get install -y python3-gi python3-dbus python3 python3-pip gir1.2-gtk-3.0
sudo pip3 install bjarkan
```

### Manual Python
```
sudo apt-get install -y python3-gi python3-dbus python3 python3-pip gir1.2-gtk-3.0
git clone https://github.com/willdeberry/bjarkan.git
cd bjarkan
python3 setup.py install
```

### Manual Debian Package
```
sudo apt-get install -y python3-gi python3-dbus python3 python3-pytest git-buildpackage gir1.2-gtk-3.0
git clone https://github.com/willdeberry/bjarkan.git
cd bjarkan
make deb
sudo dpkg -i ../$( awk '{ print $1 }' debian/files )
```

## Usage
```
usage: bjarkan [-h] [-j] COMMAND ...

Connect to specifed BT device

positional arguments:
    COMMAND
        pair                Pair a device (pairing will also connect)
        unpair              Unpair a device
        connect             Connect a new device
        disconnect          Disconnect a device
        paired-devices      Show all paired devices
        connected-devices   Show all connected devices
        scan                Show all currently known devices

optional arguments:
    -h, --help              show this help message and exit
    -j, --json              Change output format to json instead of plain text
```

### Pairing/Connecting
```
usage: bjarkan pair [-h] -d DEVICE

optional arguments:
    -h, --help                  show this help message and exit
    -d DEVICE, --device DEVICE  Specify the device to pair
```

**Example**
```bash
~$ bjarkan pair -d 00:11:22:33:44:55
```

### Unpair
```
usage: bjarkan unpair [-h] -d DEVICE

optional arguments:
    -h, --help                  show this help message and exit
    -d DEVICE, --device DEVICE  Specify the device to unpair
```

**Example**
```bash
~$ bjarkan unpair -d 00:11:22:33:44:55
```

### Connect
```
usage: bjarkan connect [-h] -d DEVICE

optional arguments:
    -h, --help                  show this help message and exit
    -d DEVICE, --device DEVICE  Specify the device to connect to
```

**Example**
```bash
~$ bjarkan connect -d 00:11:22:33:44:55
```

### Disconnect
```
usage: bjarkan disconnect [-h] -d DEVICE

optional arguments:
    -h, --help                  show this help message and exit
    -d DEVICE, --device DEVICE  Specify the device to disconnect from
```

**Example**
```bash
~$ bjarkan disconnect -d 00:11:22:33:44:55
```

### Paired Devices
```
usage: bjarkan paired-devices [-h]

optional arguments:
    -h, --help                  show this help message and exit
```

**Example**
```bash
~$ bjarkan paired-devices
```

### Connected Devices
```
usage: bjarkan connected-devices [-h]

optional arguments:
    -h, --help                  show this help message and exit
```

**Example**
```bash
~$ bjarkan connected-devices
```

### Scan
```
usage: bjarkan scan [-h]

optional arguments:
    -h, --help                  show this help message and exit
```

**Example**
```bash
~$ bjarkan scan
```
