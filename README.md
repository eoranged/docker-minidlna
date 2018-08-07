# minidnla in docker

This is minidlna on top of minimal debian distibution.
It can be configured with environment variables.

## Usage

Prefix any config directive of minidlna with `MINIDLNA_`
and run your container:

```
docker run -d --net=host \
    --restart unless-stopped \
    -p 8200:8200 \
    -v /path/to/media/dir:/media \
    -e MINIDLNA_MEDIA_DIR=/media \
    -e MINIDLNA_FRIENDLY_NAME=prettyname \
    -e MINIDLNA_ROOT_CONTAINER=B \
    -e MINIDLNA_NOTIFY_INTERVAL=15 \
    eoranged/minidlna
```

See: http://manpages.ubuntu.com/manpages/raring/man5/minidlna.conf.5.html for the list of configuration options.
