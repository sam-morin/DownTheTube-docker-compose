
<div align="center">
  <img src="./play-button-4210.svg" alt="Logo" width="220">

  <h1 align="center">DownTheTube | Docker Compose</h1>

  <!-- [![Docker Image CI](https://github.com/sam-morin/ArcorOCR-frontend/actions/workflows/docker-image.yml/badge.svg?branch=main)](https://github.com/sam-morin/ArcorOCR-frontend/actions/workflows/docker-image.yml)
[![Known Vulnerabilities](https://snyk.io/test/github/dwyl/hapi-auth-jwt2/badge.svg?targetFile=package.json&style=flat-square)](https://snyk.io/test/github/dwyl/hapi-auth-jwt2?targetFile=package.json)
[![Production Status](https://img.shields.io/badge/Production_Status-active-green)](https://arcorocr.com) -->

  <p align="center">
    <h3>A simple YouTube download web GUI | <a href="https://github.com/sam-morin/DownTheTube">Frontend Repo</a> | <a href="https://github.com/sam-morin/DownTheTube-python-backend">Backend Repo</a></h3>
    <a href="https://github.com/sam-morin/DownTheTube/issues">Report Bug</a>
    ·
    <a href="https://github.com/sam-morin/DownTheTube/issues">Request Feature</a>
    .
    <a href="#running">Build</a>
  </p>
</div>

<br/>

A basic YouTube viderooo downloader web GUI that runs in a docker container

### Background:
There aren't really any self-hosted YouTube video downloader web applications that I was able to find on Github. I only searched for a few minutes though, so I'm sure there are some out there, maybe.

## Objectives:
- Query: 
    Query a video via a YouTube URL and return information about the video.
- Download:
    Download a video to either the server or the server and the browser. Allow choosing the quality.


## Implemented:
- Query:
    Query a video via a YouTube URL and return information about the video.
- Download:
    Download a video to either the server or the server and the browser. Allows for choosing the quality.
    None of the available stream resolutions were progressive except for 360p. Bummer.
    1. Download video stream at the requested resolution
    2. Download the highest quality audio stream
    3. Stitch these friends together using ffmpeg
    4. Leave the video on the server in the `./downloaded-videos` folder
    5. Pass it back to the browser if requested

# Running

### Production

### 1. Clone the source and CD

Clone the docker compose repo
```shell
git clone https://github.com/sam-morin/DownTheTube-docker-compose.git && cd DownTheTube-docker-compose
```

Clone the frontend and backend
```shell
git clone https://github.com/sam-morin/DownTheTube.git && git clone https://github.com/sam-morin/DownTheTube-backend-python.git
```

### 2. Build and run frontend and backend

```shell
docker compose up -d
```

### 3. Access the web portal 

Unless you changed it, the web GUI will run on http://localhost:8001

Or if accessing from another machine on your network, for example: http://192.168.20.78:8001