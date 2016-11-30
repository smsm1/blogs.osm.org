# OpenStreetMap Blogs aggregator

This repository contains the list of feeds and the configuration required to generate the contents of [blogs.openstreetmap.org](https://blogs.openstreetmap.org).

## Requirements

The system is built using the [pluto](http://feedreader.github.io/) feed aggregation software. You can install the requirements using [bundler](http://bundler.io/) with:
```
bundle install
```

## Initial build

Run the following command to build the site for the first time:
```
bundle exec pluto build -t osm -o build
```

The contents of the feeds is stored in an SQLite database in the file `planet.db`, which is kept out of git. The site will be built into the `build` folder using the `osm` template. These static pages can then be easily served using e.g. apache, nginx or similar. The configuration to do this for blogs.openstreetmap.org is available in the [OSMF Chef repository](https://github.com/openstreetmap/chef)

## Subsequent updates

You can run the smaller update command, for example once per hour:
```
bundle exec pluto update
```
You need to run the `build` command each time there is an update of theme, or list of planet feeds.

## Theme

The OSM theme is available in the theme folder, thus is available by default. You can check this by running
```
bundle exec pluto list
```

The theme was started by taking the [blank template](https://github.com/feedreader/pluto.blank), and also merging in the [feeds template](https://github.com/feedreader/pluto.feeds)

To update the CSS in the theme, update the Sass, as documented at the start of the relevant file.
