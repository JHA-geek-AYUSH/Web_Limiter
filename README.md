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

#### ```weblimiter``` Commands

| Command | Explanation |
| ------- | ----------- |
| ```scan (--range [IP Range])``` | Scans your network for online hosts. One of the first things to do after start.<br>```--range``` lets you specify a custom IP range.<br>For example: ```scan --range 192.168.178.1-192.168.178.40``` or just ```scan``` to scan the entire subnet.
| ```hosts (--force)``` | Displays all the hosts/devices previously scanned and basic information. Shows ID for each host that is required for interaction.<br>```--force``` forces the table to be shown, even when it doesn't fit the terminal.
| ```limit [ID1,ID2,...] [Rate] (--upload) (--download)``` | Limits bandwidth of host(s) associated to specified ID. Rate determines the internet speed.<br>```--upload``` limits outgoing traffic only.<br>```--download``` limits incoming traffic only.<br>Valid rates: ```bit```, ```kbit```, ```mbit```, ```gbit```<br>For example: ```limit 4,5,6 200kbit``` or ```limit all 1gbit```
| ```block [ID1,ID2,...] (--upload) (--download)``` | Blocks internet connection of host(s) associated to specified ID.<br>```--upload``` limits outgoing traffic only <br>```--download``` limits incoming traffic only.
| ```free [ID1,ID2,...]``` | Unlimits/Unblocks host(s) associated to specified ID. Removes all further restrictions.
| ```add [IP] (--mac [MAC])``` | Adds custom host to host list. MAC-Address will be resolved automatically or can be specified manually.<br>For example: ```add 192.168.178.24``` or ```add 192.168.1.50 --mac 1c:fc:bc:2d:a6:37```
| ```monitor (--interval [time in ms])``` | Monitors bandwidth usage of limited host(s) (current usage, total bandwidth used, ...).<br>```--interval``` sets the interval after bandwidth information get refreshed in milliseconds (default 500ms).<br>For example: ```monitor --interval 1000```
| ```analyze [ID1,ID2,...] (--duration [time in s])``` | Analyzes traffic of host(s) without limiting to determine who uses how much bandwidth.<br>```--duration``` specifies the duration of the analysis in seconds (default 30s).<br>For example: ```analyze 2,3 --duration 120```
| ```watch``` | Shows current watch status. The watch feature detects when a host reconnects with a different IP address.
| ```watch add [ID1,ID2,...]``` | Adds specified host(s) to the watchlist.<br>For example: ```watch add 6,7,8```
| ```watch remove [ID1,ID2,...]``` | Removes specified host(s) from the watchlist.<br>For example: ```watch remove all```
| ```watch set [Attribute] [Value]``` | Changes current watch settings. The following attributes can be changed:<br>```range``` is the IP range to scan for reconnects.<br>```interval``` is the time to wait between each network scan (in seconds).<br>For example: ```watch set interval 120```
| ```clear``` | Clears the terminal window.
| ```quit``` | Quits the application.
| ```?```, ```help``` | Displays command information similar to this one.

## JustForPrank
 Web Limiter is compatible with your equipment and other software installed on your equipment. You are also solely responsible for the protection of your equipment and backup of your data, and the provider will not be liable for any damages you may suffer in connection with using, modifying, or distributing this software. 


