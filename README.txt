Usage:

1. Install FUSE

2.
$ go build -o recacc main.go
$ mkdir /tmp/mnt
$ recacc /tmp/mnt / | pv > access.json

A tracked filesystem mirroring `/` Will be mounted at `/tmp/mnt`.
Do the thing you want to record in /tmp/mnt, then

$ fusermount -u /tmp/mnt

This should stop the recording.

You should be able to open vis.html now to see the result (The `access.json` file
needs to be next to it).

You can publish the visualization to IPFS with `ipfs add -w access.json vis.html`

Note: `main.go` and `vis.html` contain some hardcoded parameters which can be tuned
based on needs

Example output: https://ipfs.io/ipfs/QmSn3a1NsKTJ8YWxgaVGrJbCGGUuWPfKMVZQvakc5EXgT9/vis.html

License:
Dual-licensed under MIT+Apache 2.0.

Parts of the code borrowed from go-fuse, licensed under the New BSD License.
See https://github.com/hanwen/go-fuse/blob/master/LICENSE
