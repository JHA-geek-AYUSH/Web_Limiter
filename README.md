# Web Limiter

A tool to monitor, analyze and limit the bandwidth (upload/download) of devices on your local network without physical or administrative access.

## Requirements
- Linux distribution
- Python 3 or greater

Possibly missing python packages will be installed during the installation process.

## Installation

```bash
git clone https://github.com/bitbrute/weblimiter.git
cd weblimiter
sudo python3 setup.py install
```

## Usage

Type ```weblimiter``` or ```python3 bin/weblimiter``` to run the tool.

```weblimiter``` will try to resolve required information (network interface, netmask, gateway address, ...) on its own, automatically.

#### Command-Line Arguments

| Argument | Explanation |
| -------- | ----------- |
| ```-h``` | Displays help message listing all command-line arguments |
| ```-i [Interface Name]``` | Specifies network interface (resolved if not specified)|
| ```-g [Gateway IP Address]``` | Specifies gateway IP address (resolved if not specified)|
| ```-m [Gateway MAC Address]``` | Specifies gateway MAC address (resolved if not specified)|
| ```-n [Netmask Address]``` | Specifies netmask (resolved if not specified)|
| ```-f``` | Flushes current iptables and tc configuration. Ensures that packets are dealt with correctly.|
| ```--colorless``` | Disables colored output |


## JustForPrank



