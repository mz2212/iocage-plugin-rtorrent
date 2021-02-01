# iocage-plugin-rtorrent

rTorrent iocage plugin.

## rTorrent

Download directory: `/home/rtorrent/download/`.  
't'd probably be a good idea to mount your truenas dl directory there...

## Test

```sh
fetch https://raw.githubusercontent.com/mz2212/iocage-plugin-rtorrent/master/rtorrent.json
iocage fetch -P rtorrent.json ip4_addr="interface|ipAddr"
```

## Security notices

This plugin is probably horribly insecure, as it hosts [RPC for everyone to see](https://github.com/rakshasa/rtorrent/wiki/RPC-Setup-XMLRPC#other-notes).  
Using this outside of a secure lan is probably a bad idea.  
I wouldn't recommend this plugin unless you know what you're doing.

Though... for most people it should be fairly safe, just don't open port 5000 for this jail. (◠‿◠✿) 

## Other notes...

It's probably a bad idea to use this on private trackers, as DHT is enabled by default.  
rtorrent afaik respects the 'private' flag, but the tracker might not set it.

The RPC is at port 5000, and peer listening is at port 7575

The rtorrent user is UID/GID 1000 to hopefully forego any file permission issues.

## Use case

This plugin is for those of us that already have a home webserver and would prefer to have a webui there.  
or perhaps users of [Electorrent](https://github.com/tympanix/Electorrent)