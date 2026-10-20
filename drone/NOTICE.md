# Notices

drone
Copyright (C) 2026 Franklin D. Amador. All rights reserved.

drone is proprietary software, used only under a commercial licence; see
[LICENSE.md](LICENSE.md). It is not open source.

## Components by the same author

The `drone` binary links beehive, honeycomb, beeguard and royaljelly. Their
author publishes them under a dual licence (GPL or commercial). In drone they
are supplied under drone's commercial licence, not the GPL (LICENSE.md,
section 5). Their licence files appear in THIRD_PARTY_LICENSES.txt because
that file is generated from every linked module.

## Third-party software

Each component below remains under its own license, and its copyright notice
and license text must accompany any distribution of drone in source or
binary form. The full license texts are in
[THIRD_PARTY_LICENSES.txt](THIRD_PARTY_LICENSES.txt), generated from the
modules actually linked into the `drone` binary (test-only dependencies are
not included):

```bash
(cd cmd/drone && ../../../beehive/scripts/gen-third-party-licenses.sh -o ../../THIRD_PARTY_LICENSES.txt)
```

Regenerate it whenever a dependency changes, and before a release.
`scripts/check.sh` keeps drone's own packages on the standard library; only
`cmd/drone` links the components below.

| Component | License |
|---|---|
| go-micro.dev/v6 | Apache License 2.0 |
| github.com/nats-io/nats.go, nkeys, nuid | Apache License 2.0 |
| github.com/klauspost/compress, github.com/oxtoacart/bpool | Apache License 2.0 |
| google.golang.org/protobuf, github.com/golang/protobuf | BSD 3-Clause |
| golang.org/x/crypto, net, sync, sys, text | BSD 3-Clause |
| github.com/google/uuid, github.com/miekg/dns, github.com/fsnotify/fsnotify, dario.cat/mergo | BSD 3-Clause |
| github.com/pkg/errors, github.com/russross/blackfriday/v2 | BSD 2-Clause |
| go.etcd.io/bbolt, github.com/urfave/cli/v2, github.com/cpuguy83/go-md2man/v2, github.com/xrash/smetrics, github.com/bitly/go-simplejson, github.com/patrickmn/go-cache | MIT |

The Go standard library and runtime (BSD 3-Clause, The Go Authors) are
compiled into the binary as well.

A drone unit also runs beehive's own binaries (beehive-core, beehive-comm),
which ship with beehive's NOTICE.md and THIRD_PARTY_LICENSES files.

Only permissive licences are allowed in drone's dependencies. A dependency
under the GPL, LGPL, AGPL, MPL or another copyleft licence needs a decision
before it is added.
