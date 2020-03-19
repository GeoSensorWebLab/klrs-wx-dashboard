# Technical Architecture

## ETL (Data Collection)

For ETL, the existing system will be re-used. Additional configuration will be added to Chef to import the new weather station data on a set schedule. The scheduling will be managed by Airflow, which also will do logging.

The existing ETL system can handle the additional load, but I do need to decrease the time-to-upload for ETL. This means finding the bottleneck, and possibly moving some parts of the service to AWS.

We may get the option to download from FTP or HTTP for sensor data instead of Campbell Scientific. This may be better as we can contact the providers more easily and scrape more often. If it supports HTTP caching headers for reducing bandwidth, then even better.

## Dashboard

The dashboard will use either React or Ember for the base framework. Our research lab has new React dashboard in development that might be reused, or the Ember dashboard I wrote last year with SensorThings API integration might work too. It only needs to read (GET) from SensorThings API, and this simplifies the code. MQTT will be necessary for automatic refresh. Stations (Things, Datastreams) can be hard-coded as the dashboard only needs to display a few specific sets of data.

The interface for the dashboard needs to be optimized for reading from a distance as it is displayed on a TV that *may* be lower resolution (720p or 1080p). A map may not be necessary, as it takes up space that could be better used for displaying values. It is important to show the time of last update, as well as display error messages if updates are not occurring. The latter may need a timer or check for when the latest Observations are older than an hour (or some other length of time).

The dashboard will be entirely client-side rendered in the browser. It will be hosted on Amazon S3 and served using Cloudfront which will also provide an HTTPS certificate for free. Offline support for the dashboard will be limited to an error message regarding a loss of connection, as data cannot be displayed without a connection to SensorThings API.
