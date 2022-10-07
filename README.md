# Media Cluster
Docker Media Cluster

## What is this 'Media Cluster'?
Media Cluster is a Stack of Docker Containers that aim to facilitate the Finding, Monitoring, Downloading and Viewing of Media. 

The applications used to facilitate this are: 
- [Overseerr](https://overseerr.dev/)
    - This is a frontend for Viewers to Find and Request Movies and TV Shows. 
- [Ombi](https://ombi.io/)
    - This is a frontend for Viewers to Find and Request Movies, TV Shows and Music. 
- [Radarr](https://radarr.video/)
    - This is an automation tool that will Find, Monitor and Download Movies
- [Sonarr](https://sonarr.tv/)
    - This is an automation tool that will Find, Monitor and Download TV Shows and Anime
- [Lidarr](https://lidarr.audio/)
    - This is an automation tool that will Find, Monitor and Download Music
- [Bazarr](https://www.bazarr.media/)
    - This is an automation tool that will Find, Monitor and Download Subtitles
- [Jackett](https://github.com/Jackett/Jackett)
    - THis is an index aggregator that takes the indexing load off of the FMD (Find, Monitor, Download) applications. 
- [qBittorrent](https://www.qbittorrent.org/)
    - This is a torrent downloader that will download the torrents supplied by the *arr series. 
- [Deluge](https://deluge-torrent.org/)
    - This is a torrent downloader that will download the torrents supplied by the *arr series. 
- [tdarr](https://tdarr.io/)
    - This is a transcoder that can be used to transcode media into a x265 format - saving space with minimal quality loss. 
- [Emby](https://emby.media/)
    - Emby is a media server designed to organize, play, and stream audio and video to a variety of devices.
- [Kavita](https://www.kavitareader.com/)
    - Kavita is a rocket fueled self-hosted digital library which supports a vast array of file formats.
- [Plex](https://www.plex.tv/)
    - The Plex Media Server organizes video, audio, and photos from a user's collections and from online services, and streams it to the players.
- [Tautulli](https://tautulli.com/)
    - Tautulli is a 3rd party application that you can run alongside your Plex Media Server to monitor activity and track various statistics.

## How to Setup
There are 2 ways to setup the media cluster. The reccomended way is via Portainer, for ease of use. 
### Portainer  
1. Login to your portainer instance. 
2. Enter your environment (by default, 'local')
3. Go to **Custom Templates** under **App Templates**
4. Click **'Add Custom Template'**
5. Add a title and description of the app
6. Select repository for the **Build Method**
7. Set the **Repository URL** to https://github.com/ronan-allen/mediacluster/
8. Click **Create Custom Template**
9. Then create your app using the custom template
 
### Docker Compose Fil
1. Direct yourself to ```/opt/mediacluster/```
2. Create the docker-compose.yml file in ```/opt/mediacluster/```
3. Run ```docker-compose up -d```

### Things to remember
The stack runs in the following directory:

```/opt/mediacluster```

With all of the applications and media in there also. e.g:

```/opt/mediacluster/plex/```

For the applications like plex. 

While all of the media and data is stored in the following directory: 

```/opt/mediacluster/media/```

e.g.

```/opt/mediacluster/media/movies/```

Overall, the file structure looks like so: 
```
├── mediacluster
│   ├── bazarr
│   ├── deluge
│   ├── emby
│   ├── jackett
│   ├── kavita
│   ├── lidarr
│   ├── media
│   │   ├── anime
│   │   ├── animemovies
│   │   ├── books
│   │   ├── downloads
│   │   ├── lightnovels
│   │   ├── manga
│   │   ├── manhwa
│   │   ├── movies
│   │   ├── music
│   │   └── tvshows
│   ├── ombi
│   ├── overseer
│   ├── qbittorrent
│   ├── radarr
│   ├── sonarr
│   ├── tautulli
│   └── tdarr
```

Meaning the applications such as Plex and Deluge, utilize the media directory to store all media. 

My reccomendation is to mount the ```/opt/mediacluster/media/``` directory to it's own drive or network mount. 
