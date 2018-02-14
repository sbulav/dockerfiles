# Docker file for building diameter/rtorrent-rutorrent with ARM64 support
I use it to run on my odroid c2, but it should work on rapberry pi as well.

## Usage

1. Clone repo 
```
git clone https://github.com/sbulav/dockerfiles.git
```

2. Cd to correct folder
```
cd dockerfiles/rtorrent-rutorrent-arm64/
```

3. Check Docker file, amend if necessary, then build it
```
docker build -t sbulav/alpine:arm64v8 .
```

3. Follow instructions on [docker hub](https://hub.docker.com/r/diameter/rtorrent-rutorrent/)


Happy downloading!
