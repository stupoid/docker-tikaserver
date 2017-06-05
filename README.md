# docker-tikaserver
Based on [LogicalSpark/docker-tikaserver](https://github.com/LogicalSpark/docker-tikaserver/)

This repo contains the Dockerfile to create a docker image that contains the latest Ubuntu running the Apache Tika 1.15 Server on Port 9998 using Java 8.

Out-of-the-box the container also includes dependencies for the GDAL and Tesseract OCR parsers.  To balance showing functionality versus the size of the image, this file currently installs the language packs for the following languages:
* English
* Japanese
* Thai
* Traditional Chinese

To install more languages simply update the apt-get command to include the package containing the language you required, or include your own custom packs using an ADD command.

## Building

To build the image from scratch, simply invoke:

    docker build -t 'docker-tikaserver' github.com/stupoid/docker-tikaserver

You can then use the following command (using the name you allocated in the build command as part of -t option):

    docker run -d -p 9998:9998 docker-tikaserver

## More

For more info on Apache Tika Server, go to the [Apache Tika Server documentation](http://wiki.apache.org/tika/TikaJAXRS).
