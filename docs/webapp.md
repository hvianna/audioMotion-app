# Running as a Web App

audioMotion can also run in your web browser, in three different server scenarios:

- serverless, in [local file mode](#local-file-mode) with limited capabilites;
- using its own [custom file server](#custom-file-server) (preferred);
- hosted in a [standard web server](#standard-web-server) like Apache, Lighttpd or Nginx.

[Clone the project](https://github.com/hvianna/audioMotion.js) from GitHub or download the latest version of the source code from the [Releases page](https://github.com/hvianna/audioMotion.js/releases/latest).

## Local file mode

You can run audioMotion in **file mode** by directly opening the `index.html` file located inside the `public` folder.

In this mode you can play individual music files from your computer or from a remote URL and use the microphone input,
but neither the file explorer or the playlist functionalities will be available.

## Custom file server

audioMotion's custom file server allows the web app to access music files from a selected folder in your hard disk.

You'll need [Node.js](https://nodejs.org) installed in your computer to run the server.

Install the required packages (first time only) with:

```
npm install
```

And then start the server by running:

```
npm run server -- -m /path/to/music
```

Where `/path/to/music` is the full path to your music folder (in Windows machines the path will look like `c:\user\myUser\music`).

You should then be able to access audioMotion at `localhost:8000` on your web browser.

By default, the server will only accept connections from *localhost*. If you'd like other computers in your network to access the web app, you can start the server with the `-e` argument:

```
npm run server -- -e -m /path/to/music
```

The complete command line options are:

```
-b <path> : path to folder with background images and videos
-e        : allow external connections (by default, only localhost)
-m <path> : path to music folder
-p <port> : change server listening port (default is 8000)
-s        : start server only (do not launch client)
```

!> **WARNING:**<br>
Please be aware that using the `-e` flag will expose the contents of the mounted folders to anyone in your network (and potentially to the entire internet!) &mdash; use it only if you're in a trusted network and behind a firewall!

## Standard web server

You can also use audioMotion with a standard web server, like Apache, Lighttpd or Nginx.

This is an alternative way to play music stored, for example, in older NAS servers not capable of running Node.js.

Just copy the `public` folder to your server (you can rename it to **audioMotion** for instance) and make the necessary configurations:

* Assign a dedicated listening port to audioMotion so it can be accessed at the server's root and not from a subdirectory:<br>
  ✔️ `http://192.168.0.32:8000`<br>
  ❌ `http://192.168.0.32/audioMotion` (won't work!)
* Directory listing must be enabled for the file explorer to work;
* Add your music files to the `music` folder or map the `/music` URL to another folder in your server (see examples below);
* Optionally, image and video files added to the `backgrounds` folder will be available as background options in the player Settings.

### Configuration tips <!-- {docsify-ignore} -->

**Lighttpd:**

```
$SERVER["socket"] == ":8000" {
    server.document-root = "/mnt/HD/HD_a2/web/audioMotion/"
    dir-listing.activate = "enable"
    alias.url += ( "/music/" => "/mnt/HD/HD_a2/MUSIC/" )
}
```

**Apache:**

```
Listen 8000

<VirtualHost *:8000>
    DocumentRoot "/mnt/HD/HD_a2/web/audioMotion/"
</VirtualHost>

Alias "/music" "/mnt/HD/HD_a2/MUSIC"

<Directory "/mnt/HD/HD_a2/MUSIC">
    Options Indexes FollowSymLinks
</Directory>
```

**Nginx:**

*To do...*

### Apache web server with Docker <!-- {docsify-ignore} -->

If you use Docker, you can simply open a command prompt in audioMotion's directory and run:

`docker-compose up -d`

and you should be able to access audioMotion via HTTP by entering `localhost:8000` in your browser.

The provided configuration file maps the folder "music" in your user directory to the web server document root, so audioMotion can access files inside it as "music/song.mp3", for example.
This should work for the default "Music" folder on Windows. If you want to map a different folder or drive, edit the line below in `docker-compose.yml`:

```
    - ~/music:/usr/local/apache2/htdocs/music/
```

and change `~/music` for your desired local path, for example `j:\media\music` or `/j/media/music`. **Do not** change the path after the colon.

On Windows, if you're using a drive other than C: you might need to add it to the shared drives in Docker's configuration.

## Additional notes for usage on web browsers

?> Your **Presets, Playlists** and **Custom gradients** are saved to your browser's local storage and will only be accessible in the
same browser they were saved. Browser local storage is also relative to the server port, so if you change the server port you won't be
able to access previously saved data.

* The [PIP button](users-manual.md#top-panel-buttons) will be disabled on browsers that don't support the Picture-In-Picture API

### Microphone input

Browser access to the microphone is only allowed in a secure context, i.e., a page acessed via HTTPS protocol,
or from *localhost* or a local HTML file (file://).

If your sound card supports *Stereo mix* mode, this option may be listed as an input device when you set the Source to MIC.
The *Stereo mix* input allows audioMotion to read audio generated by any program running in your PC.

### Playlists

Saved playlists appear in the playlist selection box.

Select a playlist and click one of the buttons:

| Button | Action |
|:-------|:-------|
| **Load** | Load the selected playlist, **adding** its contents to the end of the current queue |
| **Save** | Update the selected playlist with the current queue contents |
| **Delete** | Permanently delete the selected playlist |

## Browser-specific known issues

* On **Firefox**, [Fill Opacity](users-manual.md#line-width-and-fill-opacity) may not work properly with [Radial](users-manual.md#radial) analyzer, due to [this bug](https://bugzilla.mozilla.org/show_bug.cgi?id=1164912);
* Visualization of live streams currently don't work on **Safari**, as documented in [this bug report](https://bugs.webkit.org/show_bug.cgi?id=195043).
