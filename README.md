
docker create \
--name plex --net=host --restart=always \
-e TZ="America/New York" \
-e PUID=1000 -e PGID=1000 \
-e PLEX_CLAIM="<CLAIM>" \
-p 32400:32400 \
-v /docker/containers/plex/config:/config \
-v /docker/containers/plex/transcode:/transcode \
-v /mnt/music:/data/music:shared \
-v "/mnt/media/TV Shows":/data/tvshows:shared \
-v /mnt/bollywood:/data/bollywood:shared \
-v /mnt/hollywood:/data/movies:shared \
 plexinc/pms-docker:plexpass
