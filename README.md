# refidtool

[![Build Status](https://github.com/dropwhile/refidtool/workflows/unit-tests/badge.svg)][1]
[![GoDoc](https://godoc.org/github.com/dropwhile/refidtool/v2?status.png)](https://godoc.org/github.com/dropwhile/refidtool/v2)
[![Go Report Card](https://goreportcard.com/badge/github.com/dropwhile/refidtool/v2)](https://goreportcard.com/report/github.com/dropwhile/refidtool/v2)
[![License](https://img.shields.io/github/license/dropwhile/refidtool.svg)](https://github.com/dropwhile/refidtool/blob/master/LICENSE.md)

## About

A cli tool for [refid](https://github.com/dropwhile/refid).

## Installation

```sh
go install github.com/dropwhile/refidtool/v2@latest
```

## Usage

```sh
# generate a refi.ID with a tag of 5
% refidtool generate -t 5
native enc:   1hh3ecgwmg40ahtaf41qc1dz88
hex enc:      0c6237321ca40805474a79037605bf42
base64 enc:   DGI3MhykCAVHSnkDdgW_Qg
tag value:    5
type:         TimePrefixed
time(string): 2023-12-08T00:49:04.916Z
time(millis): 1701996544916

# generate a refid with a tag of 5, and only output the native(base32) encoding
% refidtool generate -t 5 -o native
1hh3ecvn3dt0bs66r6p6q4gqe0

# generate a refid with a tag of 5, and only output the hex encoding
% refidtool generate -t 5 -o hex
0c6237347678a60554f8b73f96992fed

# generate a random-prefixed refid with a tag of 4, and only output the base64 encoding
% refidtool generate -r -t 4 -o base64
KRUV6EEACQRsivT1_pNr4w

# genrate a refid with a tag of 2, at a specific timestamp
% refidtool generate -t 2 -w "2023-01-01T00:00:11.123456Z"
native enc:   1gnna1wvkbx047v48dhxeh7c5g
hex enc:      0c2b55079b9afa021f644363d744ec2c
base64 enc:   DCtVB5ua-gIfZENj10TsLA
tag value:    2
type:         TimePrefixed
time(string): 2023-01-01T00:00:11.123Z
time(millis): 1672531211123

# decode a refid and display
% refidtool parse 1hh3eehsh2p05ycz44y9erhvhm
native enc:   1hh3eehsh2p05ycz44y9erhvhm
hex enc:      0c62373a3988ac02f99f213c97623b8d
base64 enc:   DGI3OjmIrAL5nyE8l2I7jQ
tag value:    2
type:         TimePrefixed
time(string): 2023-12-08T00:50:11.377Z
time(millis): 1701996611377

# here is what a random-prefixed refid looks like
# note the time is the zero value for time.Time
% refidtool parse 8xqzbn495crg5mxjztjczfk0xr
native enc:   8xqzbn495crg5mxjztjczfk0xr
hex enc:      476ff5d4892b3102d3b2fea4cfbe60ee
base64 enc:   R2_11IkrMQLTsv6kz75g7g
tag value:    2
type:         RandomPrefixed
time(string): 1970-01-01T00:00:00Z
time(millis): 0
```

[1]: https://github.com/dropwhile/refidtool/actions