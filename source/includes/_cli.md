#  IPFinder CLI (Command Line Interface)
-  Supports Single IP Address, asn, ranges, firewall as Input
-  Supports Bulk
-  Exports Results to Screen or to An Output File
-  Supports IPv4 and IPv6
-  Supports ASN number , RANGES , Firewall

## Installation
### Via composer
First, download the IPfinder cli using Composer:
```
composer global require ipfinder-io/ip-finder-cli
```

### Linux Distributions / macOS

```
## using curl

$ curl -LO https://github.com/ipfinder-io/ip-finder-cli/releases/download/v1.0.2/ipfinder.phar
## using wget
$ wget https://github.com/ipfinder-io/ip-finder-cli/releases/download/v1.0.2/ipfinder.phar
$ chmod +x ipfinder.phar
$ sudo mv ipfinder.phar /usr/bin/ipfinder
$ ipfinder -h
```

### Windows
1.  Download [IPFINDER PHAR](https://github.com/ipfinder-io/ip-finder-cli/releases/download/v1.0.2/ipfinder.phar) from github
2.  Create a directory for PHP binaries; e.g., `C:\bin`
3.  Open a command line (e.g., press **Windows+R** » type `cmd` » ENTER)
4.  Create a wrapping batch script (results in `C:\bin\ipfinder.cmd`):

```
C:\Users\username> cd C:\bin
C:\bin> echo @php "%~dp0ipfinder.phar" %* > ipfinder.cmd
C:\bin> exit
```
5. Open a new command line and confirm that you can execute IPfinder from any path:
```
C:\Users\username> ipfinder --help
````

## Command list

| shortopts   | longopts     | Description
| ----------- | -----------  |-----------
| `-h`      | `--help`    | This help text
| `-o`      | `--output`  |  save to a given file
| `-u`      | `--update`  | App Code update
| `-a`      | `--auth`  |  lookup your IP address information.
| `-m`      | `--format`  | fetching IP address information.
| `-i`      | `--ip`  | firewall  supported format https://ipfinder.io/docs/?shell#firewall.
| `-n`      | `--asn`  | fetching AS number information.
| `-r`      | `--ranges`  | fetching IP Address Ranges information.
| `-f`      | `--firewall`  | fetching firewall information
| `-d`      | `--domain`  | Get information for Domain IP.
| `-d`      | `--dhistory`  | Get information for Domain IP history.
| `-dl`     | `--dlist`  | Get information for list Domain By ASN, Country,Ranges.
| `-s`      | `--status`  |  Get information for your token.
| `-c`      | `--config`  | Add your Token and lang
| `-l`      | `--shell`  | Run interactively
