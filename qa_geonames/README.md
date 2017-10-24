# Overview

This document describes how access GeoNames authority to work with linked data. 

## GeoNames vocabulary

The GeoNames geographical database covers all countries and contains over eleven million placenames that are available for download free of charge.

[More Information](http://www.geonames.org/)


# Usage

The configurations in `config/authorities/linked_data` directory are designed to work with [ld4l-labs/qa_server](https://github.com/ld4l-labs/qa_server) to provide normalized access and data results.  See the [ld4l-labs/linked_data_authorities documentation](https://github.com/ld4l-labs/linked_data_authorities/blob/master/README.md) for more information on setting up a qa_server.

## Supported Configurations

* geonames_direct.json - Provides a configuration for directly accessing the GeoNames vocabulary as provided by GeoNames.
* geonames_ld4l_cache.json - Provides a configuration for accessing the LD4L-Labs cache of the GeoNames vocabulary.

[Technical Documentation](http://www.geonames.org/export/geonames-search.html)
[Download](http://www.geonames.org/ontology/documentation.html) (custom format – see notes for processing)

NOTE: GeoNames download…  At the end of the Entry Points section of http://www.geonames.org/ontology/documentation.html there is a link to a file containing "RDF".  The file is a pair of repeating lines, a URI and a single RDF/XML document as a string as a second line.  I had to write a loader program that reads the file, parses the even numbered lines into models and then emit the models as n-triples to feed into fuseki.  See [qa_geonames/script/Loader.java](https://github.com/ld4l-labs/linked_data_authorities/blob/master/script/Loader.java)