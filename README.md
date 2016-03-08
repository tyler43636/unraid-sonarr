# Application
[Sonarr](https://sonarr.tv/)

# Description
Sonarr is a PVR for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new episodes of your favorite shows and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.

# Access application
`http://<host ip>:8989`

# Run the application
The ```PUID``` and ```PGID``` values are not necessary for unRAID 6.
## Usage
Please replace all user variables in the below command defined by ```<>``` with the correct values.
```
docker run -d \
  --name=<container name> \  
  -v <path for config files>:/config \
  -v <path for downloads and media>:/data
  -v /etc/localtime:/etc/localtime:ro \
  -p <port>:8989 \
  -e PUID=<uid for user> \
  -e PGID=<gid for user> \
  tyler43636/unraid-sonarr
```

## Example
```
docker run -d \
  --name=sonarr \
  -v /config:/config \
  -v /storage:/data
  -v /etc/localtime:/etc/localtime:ro \
  -p 8989:8989 \
  -e PUID=99 \
  -e PGID=100 \
  tyler43636/unraid-sonarr
```

# Notes
User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:
```
id <username>
```
