## About

![audioMotion-header](img/audioMotion-header.png)

> **audioMotion** is a high-resolution real-time audio spectrum analyzer and full-featured music player that lets you **see your music!** ♪♫🤩<br>
> It is completely free, open-source software, created out of my passion for the graphic spectrum analyzers of hi-fi systems from the 1980s.

## Features

* High-resolution real-time dual channel audio spectrum analyzer
* Fullscreen and Picture-In-Picture support at 60fps, ready for retina / HiDPI displays
* Logarithmic, linear and perceptual (Bark and Mel) frequency scales, with customizable range
* Visualization of discrete FFT frequencies or up to 240 frequency bands (supports ANSI and equal-tempered octave bands)
* Decibel and linear amplitude scales, with customizable sensitivity
* Optional A, B, C, D and ITU-R 468 weighting filters
* Optional effects: vintage LEDs, variable opacity, mirroring and reflection, radial visualization
* 17 beautiful color gradients, plus a visual editor to easily create your own gradients
* HTML5 audio player for MP3, AAC (m4a), OGG and FLAC files (support may vary depending on browser and operating system)
* Visual file explorer and play queue with drag-and-drop functionality
* Support for M3U playlists (`m3u` and `m3u8` file extensions)
* Visualize audio from your microphone (or "stereo mix", if your soundcard supports it)
* Lightweight custom file server — also works on standard web servers with minimal configuration
* Client runs on any modern browser (tested on Chrome, Firefox, Opera and Safari)

?> **For developers:**<br>Check out [**audioMotion-analyzer**](https://audiomotion.dev) for easy integration of audioMotion's full-featured spectrum analyzer into your own Javascript projects!

## Demo

> ▶ **[https://demo.audiomotion.me](https://demo.audiomotion.me)**

The demo site includes a few sample songs, radio streams and background images and videos ([credits here](#resources-used-in-the-demo-site)).

You can also upload audio files from your PC and use the microphone input.

Also check out our [**YouTube channel**](https://audiomotion.me/yt) for some cool songs visualized with audioMotion!

## Getting started

Download the latest version from the [**Releases page**](https://github.com/hvianna/audioMotion.js/releases/latest).

Binaries are available for Windows, Linux and macOS (Intel x64) - these are not signed, so you'll get the usual warnings from your operating system.

Verify the integrity of binaries using the commands below. Check the generated checksums against the ones provided in the release page.

+ Windows:
```
certutil -hashfile "audioMotion-23.8.0 Setup" md5
certutil -hashfile "audioMotion-23.8.0 Setup" sha256
```

+ Linux:
```
md5sum filename
sha256sum filename
```

+ MacOS:
```
md5 filename
shasum -a 256 filename
```

?> You don't need binaries to run **audioMotion** in a web browser. Check [Running as a Web App](webapp.md) for more information.

If you want to build your own binaries, check the [Building](building.md) page.

## Credits

### Special thanks <!-- {docsify-ignore} -->

I would like to thank my wife **Virginia** for her continued support, encouragement and feedback! :kissing_heart:

[Yuji Koike](https://www.ykcircus.com/) for his great [Soniq Viewer for iOS](https://itunes.apple.com/us/app/soniq-viewer/id448343005), which inspired me to create **audioMotion.**

And all the developers and content creators for the resources listed below.

### JavaScript libraries <!-- {docsify-ignore} -->

Some of audioMotion's great features are provided by these awesome open-source libraries:

* [buffer](https://www.npmjs.com/package/buffer) - Node.js Buffer API, for the browser
* [express](https://www.npmjs.com/package/express) - fast, unopinionated, minimalist web framework for node
* [idb-keyval](https://www.npmjs.com/package/idb-keyval) - super-simple promise-based keyval store implemented with IndexedDB
* [music-metadata-browser](https://www.npmjs.com/package/music-metadata-browser) - stream and file based music metadata parser for the browser
* [notie](https://www.npmjs.com/package/notie) - clean and simple notification, input, and selection suite for javascript, with no dependencies
* [open](https://www.npmjs.com/package/open) - open stuff like URLs, files, executables
* [pkg](https://www.npmjs.com/package/pkg) - single-command Node.js binary compiler
* [process](https://www.npmjs.com/package/process) - process information for node.js and browsers
* [readline-sync](https://www.npmjs.com/package/readline-sync) - synchronous Readline for interactively requesting user input via console
* [scrollIntoViewIfNeeded 4 everyone](https://gist.github.com/hsablonniere/2581101) - polyfill for non-standard scrollIntoViewIfNeeded() method
* [serve-index](https://www.npmjs.com/package/serve-index) - serve directory listings
* [sortablejs](https://www.npmjs.com/package/sortablejs) - JavaScript library for reorderable drag-and-drop lists
* [webpack](https://www.npmjs.com/package/webpack) - JavaScript module bundler for the browser
  * [css-loader](https://www.npmjs.com/package/css-loader) - CSS loader module for webpack
  * [css-minimizer-webpack-plugin](https://www.npmjs.com/package/css-minimizer-webpack-plugin) - cssnano plugin for Webpack
  * [mini-css-extract-plugin](https://www.npmjs.com/package/mini-css-extract-plugin) - extracts CSS into separate files

### Graphic resources <!-- {docsify-ignore} -->

* Fonts [Orbitron](https://github.com/theleagueof/orbitron), [Jet Brains Mono](https://github.com/JetBrains/JetBrainsMono) (_from [Google Fonts](https://fonts.google.com/specimen/JetBrains+Mono)_) and
[Sofia-Sans Semi-Condensed](https://github.com/lettersoup/Sofia-Sans) licensed under the [SIL Open Font License](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ofl)
* Icons provided by [icons8](https://icons8.com) licensed under [Creative Commons Attribution-NoDerivs 3.0 Unported](https://creativecommons.org/licenses/by-nd/3.0/)
* [Mouse scroll icon](https://thenounproject.com/term/mouse-scroll/628146/) by Viktor Ostrovsky, licensed under [Creative Commons CCBY](https://creativecommons.org/licenses/by/3.0/us/legalcode)
* Gradients *Prism* and *Rainbow* use the [12-bit rainbow palette](https://iamkate.com/data/12-bit-rainbow/) by Kate Morley
* Gradients [*Candy*](https://gradienthunt.com/gradient/172), [*Miami*](https://gradienthunt.com/gradient/950), [*Outrun*](https://gradienthunt.com/gradient/317) and [*Tie Dye*](https://gradienthunt.com/gradient/969) from [Gradient Hunt](https://gradienthunt.com)
* Gradients *Pacific Dream*, *Shahabi*, *Summer* and *Sunset* from [uiGradients](https://uigradients.com)
* The *Apple &#93;&#91;* gradient was created based on [this post](https://creativemarket.com/blog/6-famous-logos-with-great-color-schemes) by Creative Market
* Gradients used in the UI buttons are from [ColorZilla's Ultimate CSS Gradient Generator](http://www.colorzilla.com/gradient-editor/)
* [CSS3 inset text shadow](https://codepen.io/adambundy/pen/HtmaK) by Adam Bundy
* [CSS slider switches](https://codepen.io/billyysea/pen/CHmiE) by Billy
* Radial brushed metal texture taken from [this pen](https://codepen.io/GreenSock/pen/gnoDc) by GreenSock
* Knobs design based on [Dark dial](https://codepen.io/stormwarning/pen/yNGeMm) by Jeff
* Warp effects based on [this pen](https://codepen.io/trangthule/pen/vYmpNYR) by bytrangle

### Resources used in the demo site <!-- {docsify-ignore} -->

* Background images
  * "Band Performing on Stage" by [Vishnu R Nair](https://unsplash.com/@vishnurnair?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)
  * "Jewels of the Queen Cassiopeia" by [Aldebaran S](https://unsplash.com/@aldebarans?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/nebula?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)
  * "Music Room" by [John Matychuk](https://unsplash.com/@john_matychuk?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)
  * "Water Droplets on Glass Window" by [Aleksandar Pasaric](https://www.pexels.com/@apasaric?utm_content=attributionCopyText&amp;utm_medium=referral&amp;utm_source=pexels) from [Pexels](https://www.pexels.com/photo/water-droplets-on-glass-window-2068411/?utm_content=attributionCopyText&amp;utm_medium=referral&amp;utm_source=pexels)
* Background videos
  * ["Flying Above Clouds"](https://www.youtube.com/watch?v=XIhEPwTMjWk) by [Relaxation Windows 4K Nature](https://www.youtube.com/channel/UC-he8--TRguZ-nNUSiH77Uw)
  * ["Smoke and Sparks"](https://www.youtube.com/watch?v=672TY8K2PKk) by [MG1010](https://youtube.com/MG1010)
  * ["Starfield"](https://www.youtube.com/watch?v=dpVFhuoeMpI) and ["Synthwave Landscape"](https://www.youtube.com/watch?v=3cKq_qBsEQU) by [Facta Non Verba Designs](http://bit.ly/FactaNonVerbaDesignsYT)
* Music
  * ["Funky Chunk"](https://incompetech.com/music/royalty-free/index.html?isrc=USUAN1500054) by [Kevin MacLeod](https://incompetech.com) - Licensed under [Creative Commons: By Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/)
  * ["Spell"](https://archive.org/details/Straw_Fields-8753) by [Rolemusic](http://rolemusic.sawsquarenoise.com/) - Licensed under [Creative Commons: By Attribution NonCommercial ShareAlike 3.0 US License](https://creativecommons.org/licenses/by-nc-sa/3.0/us/)
  * ["The Factory"](https://archive.org/details/The_Factory-3613) by [Multifaros](http://multifaros.info.se/) - Licensed under [Creative Commons: By Attribution 3.0 US License](https://creativecommons.org/licenses/by/3.0/us/)
  * ["We Come Together"](https://archive.org/details/ShMusic-DigitalMemories) by [Lukhash](https://lukhash.com) - Licensed under [Creative Commons: By Attribution NonCommercial NoDerivatives 3.0 License](https://creativecommons.org/licenses/by-nc-nd/3.0/)
  * Web radios: [Classic FM](https://classicfm.com), [Dance Wave!](https://dancewave.online), [Ibiza Global Radio](https://ibizaglobalradio.com), [jazz 4 ever](http://jazz4ever.net), [Nightride FM](https://nightride.fm)

### References <!-- {docsify-ignore} -->

These online references were invaluable for the development and improvement of audioMotion:

* [HTML Canvas Reference @W3Schools](https://www.w3schools.com/tags/ref_canvas.asp)
* [Web Audio API documentation @MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
* [Web Audio API Specification](https://webaudio.github.io/web-audio-api/)
* [What does the FFT data in the Web Audio API correspond to?](https://stackoverflow.com/a/14789992/2370385)
* [HTML5 check if audio is playing?](https://stackoverflow.com/a/46117824/2370385)
* [Unlocking Web Audio — the smarter way](https://hackernoon.com/unlocking-web-audio-the-smarter-way-8858218c0e09)
* [Equations for equal-tempered scale frequencies](http://pages.mtu.edu/~suits/NoteFreqCalcs.html)
* Pure CSS modal windows based on [this pen](https://codepen.io/timothylong/pen/HhAer) by Timothy Long and [CSS Modal](https://drublic.github.io/css-modal/) by Hans Christian Reinl

## License

audioMotion.js copyright (c) 2018-2023 [Henrique Avila Vianna](https://henriquevianna.com)<br>
Licensed under the [GNU Affero General Public License, version 3 or later](https://www.gnu.org/licenses/agpl.html).

---

This website is powered by [GitHub Pages](https://pages.github.com/), [docsify](https://docsify.js.org/) and [docsify-themeable](https://jhildenbiddle.github.io/docsify-themeable).
