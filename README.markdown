# KLRS Weather Station Dashboard

A non-interactive web-hosted dashboard for displaying local weather conditions using SensorThings API.

One weather station is located at Kluane Lake Research Station in Yukon, Canada. The second weather station is located on a nearby glacier.

The dashboard is non-interactive as it is intended to be displayed on a TV for reference, similar to a TV channel that displays weather conditions. For this reason the dashboard will automatically cycle through different observed properties and locations to allow someone to see the recent values without having to control the dashboard with a mouse or touchscreen.

Data from the weather stations is uploaded to Campbell Scientific or a private host using a WiFi or Satellite internet connection. The GeoSensorWeb Lab at the University of Calgary runs a cloud service that automatically retrieves the latest data from those sources and converts it to SensorThings API entities, after which it is uploaded to a public SensorThings API service hosted by SensorUp Inc.

Additional documentation regarding use cases and technical architecture are located in the `docs` directory.

## Using the Dashboard

The dashboard will be hosted on Amazon S3; the URL will be posted HERE when it is available.

TODO: Explain what data is available on the dashboard to someone who just wants to view the weather conditions

## Development

TODO: Instructions for setting up a development environment for modifying the dashboard

## Deployment

TODO: Instructions for deploying the dashboard on Amazon S3 or to a self-hosted HTTP server

## License

All code released under the MIT License. Documentation is Creative Commons [Attribution-NonCommercial 4.0 International](http://creativecommons.org/licenses/by-nc/4.0/).

## Authors

James Badger (<jpbadger@ucalgary.ca>)
