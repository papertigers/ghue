[![Build Status](https://travis-ci.org/yesnault/ghue.svg?branch=master)](https://travis-ci.org/yesnault/ghue)
[![GoDoc](https://godoc.org/github.com/yesnault/ghue?status.svg)](https://godoc.org/github.com/yesnault/ghue)


# Alpha Version, WORK IN PROGRESS

# Description
Golang Hue SDK & Command Line Interface


# Usage

## General Rules

A successful command will give you no feedback. If you want one, you can use `-v` argument.
After each command, the exit code can be found in the `$?` variable. No error if exit code equals 0.

## Quick Start

- Get IP of your bridge. See http://www.developers.meethue.com/documentation/getting-started to check how to discover your bridge's IP.
- Press button on your bridge
- If your IP is `192.168.0.17`, execute `./ghue config create --ip 192.168.0.17 --save`
- Get All yours lights, execute `./ghue lights all`
- Switch Off a light : `./ghue lights state 1 --on=false`
- Switch On a light : `./ghue lights state 1 --on=true`
- Switch On a light and set brightness to minimum : `./ghue lights state 1 --on=true --bri=1`
- View all other lights parameters : `./ghue lights state -h`


## Documentation

```
Usage:
  ghue [command]

Available Commands:
  config      Config commands: ghue config --help
  lights      Lights commands: ghue lights --help
  update      Update ghue to the latest release version: ghue update
  version     Display Version of ghue: ghue version

Flags:
  -c, --configFile string   configuration file, default is /Users/yvonnickesnault/.ghue/config.json (default "/Users/yvonnickesnault/.ghue/config.json")
  -f, --format string       choose format output. One of 'json', 'yaml' and 'pretty' (default "pretty")
  -v, --verbose             verbose output
```

# Hacking

Ghue is written in Go 1.5, using the experimental vendoring
mechanism introduced in this version. Make sure you are using at least
version 1.5.

```bash
mkdir -p $GOPATH/src/github.com/yesnault
cd $GOPATH/src/github.com/yesnault
git clone git@github.com:yesnault/ghue.git
cd $GOPATH/src/github.com/yesnault/ghue
export GO15VENDOREXPERIMENT=1
go build
```
