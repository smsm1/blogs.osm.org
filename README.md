#OpenStreetMap Blogs listing
Code for blogs.osm.org 

## Intro

Main scripts for updating the OSM blogs instance running on the [pluto software](http://feedreader.github.io/).

## Requirements
Install the ruby requirements (assuming bundler is already installed)
```
bundle install
```

## Initial build

Run the following command to build the site for the first time:
```
pluto build -t osm -o build
```

The site will be built into the build folder using the osm template. The information about the feeds is stored in an SQLite database in the file planet.db, which is kept out of git.

## Subsequent updates

Thereafter you run the smaller update command each say hour:
```
pluto update
```
You need to run the build command each time there is an update of theme, or list of planet feeds.

## Theme

The OSM theme is avilable in the theme folder, thus is available by default. You can check this by running 
```
pluto list
```

The theme was started by taking the [blank template](https://github.com/feedreader/pluto.blank), and also merging in the [feeds template](https://github.com/feedreader/pluto.feeds)

To update the CSS in the theme, update the Sass, as documented at the start of the relevant file.
