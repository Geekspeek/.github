# Geekspeek Communication App
A decentralized form based communication app. Each form is a self-contained server hosted by the server owner.  Neither the server nor any of the clients will "phone home" or a central server for any reason other than to check for updates and this will be hosted via GitHub.
# Server
The server will be completely configurable and customizable.
## Settings
- Set the max audio and video bitrate
- Set the max screen-share resolution and framerate
- Set the max video resolution and framerate
- Customize servers appearance using HTML/CSS
- Set the max file upload size (per file extension or globally)
- Whitelist/Blacklist file extensions
- Whitelist/Blacklist link domains
- Allow/disallow sharing system audio when screen-sharing
- Allow/disallow users to take control of other users computers (like teamviewer or parsec)
	- This could be used to tech help or to play split-screen games
- Set the screen share method to be peer-to-peer or server passthrough
- Set the level of compression that the screen share and video streams should under go and if they should be compressed client, server side or both.
- Allow/disallow markdown messaging support
- Allow/disallow end-to-end data encryption
- Set max message history or allow unlimited message history
## Stack
The server will be a REST API built in ASP.NET 8.0 using C#. The server will contain **NO** front-end code or styling.  The database will be [SQLite](https://www.sqlite.org/) . For client communication a mixture of websockets and polling will be utilized depending on the importance of the information.

# Client
The client will be the dashboard to view all the servers you are a part of.
## Authentication
The client will use various OAuth options:
- Microsoft OAuth
- GitHub OAuth
- Google OAuth
There will **NOT** be any first party authentication system for a mixture of security and decentralization.
## Caching
All information will be cached to improve application speed and decrease unnecessary network traffic.  The max size of the cache is configurable to reduce unwanted storage usage.  The caching system will use a custom lightweight checksum/file-time comparison system.
Items that will be cached include:
- Embedded images
- Video Thumbnails
- Profile Images
- Server Icons
- Server Themes (HTML/CSS)
## Stack
The client will be written using [Rust](https://www.rust-lang.org/) with the [TAURI](https://tauri.app/) framework.  [Typescript](https://www.typescriptlang.org/), [Sass](https://sass-lang.com/) and [jQuery](https://jquery.com/) for the front end. [FFMPEG](https://ffmpeg.org)will be utilized for capturing audio, video, and screens, it will also be used to compress cached media files.
