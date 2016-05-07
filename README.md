# spotify-finder

A Spotify Client for Node.js (non promised)
It allows to use some [Spotify Web API](https://developer.spotify.com/web-api/) endpoints

## Install
```
$ npm install spotify-finder
```
## Usage

``` js
var spotify = require('spotify-finder')
var client = spotify.createClient({
  client_id: 'YOUR_CLIENT_ID', // if your not have an app in spotify ignore this options
  client_secret: 'YOUR_CLIENT_SECRET' // if your not have an app in spotify ignore this options
})
```
Note: if you do not Provide the client credentials, some features that require authentication will not be available.
To create an application in spotify. [click here](https://developer.spotify.com/my-applications/#!/)

#### Search for all types
```js
client.search('Demi', 'all', 10, function (err, data) {
  // do something with data
})
```
Parameter 'Demi' is search, 'all' type of search '10' limit of results.
##### types alowed:
* artists
* albums
* tracks
* all

#### Search for type specific
```js
client.search('Stone Cold', 'track', 2,  function (err, tracks) {
  // do something with tracks
})
```

#### Get a List of New Releases
```js
client.browse({ newReleases: true }, function (err, albums) {
  // do something with album's
})
```
#### Get a List of Featured Playlists
```js
client.browse({ featuredPlaylists: true }, function (err, playlists) {
  // do something with playlist's
})
```
#### Get a List of Categories
```js
client.browse({ categories: true }, function (err, categories) {
  // do something with categories
})
```

#### Get album by id
```js
client.getAlbum('41MnTivkwTO3UUJ8DrqEJJ', { tracks: false }, function (err, album) {
  // do something with album
})
```
#### Get an album's tracks
```js
client.getAlbum('41MnTivkwTO3UUJ8DrqEJJ', { tracks: true }, function (err, tracks) {
  // do something with tracks
})
```

#### Get several albums by id
```js
client.getAlbums(['41MnTivkwTO3UUJ8DrqEJJ', '6UXCm6bOO4gFlDQZV5yL37'], function (err, albums) {
  // do something with albums
})
```

#### Get artist by id
```js
client.getArtist('6S2OmqARrzebs0tKUEyXyp', {}, function (err, artist) {
  // do something with artist
})
```

#### Get an artist's albums
```js
client.getArtist('6S2OmqARrzebs0tKUEyXyp', { albums: true }, null, function (err, albums) {
  // do something with albums
})
```

#### Get an artist's top tracks
```js
client.getArtist('6S2OmqARrzebs0tKUEyXyp', { topTracks: true }, null, function (err, tracks) {
  // do something with tracks
})
```

#### Get an artist's related artists
```js
client.getArtist('6S2OmqARrzebs0tKUEyXyp', { relatedArtists: true }, null, function (err, artists) {
   //do something with artists
})
```

#### Get several artists by id
```js
client.getArtists(['15deb326635d69d0505434', '934da7155ec15deb32663'], function (err, artists) {
  //do something with artists
})
```

#### Get an track by id
```js
client.getTrack('934da7155ec15deb32663', function (err, track) {
  //do something with track
})
```

#### Get several tracks by id
```js
client.getTracks(['15deb326635d69d0505s', 'da7155ec15deb326635d69d'], function (err, tracks) {
  //do something with tracks
})
```
## License MIT

Copyright (c) 2016 - Luis Lacruz


Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:


The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.


THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
