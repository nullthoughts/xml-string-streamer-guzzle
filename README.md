xml-string-streamer-guzzle [![Build Status](https://travis-ci.org/prewk/xml-string-streamer-guzzle.svg?branch=master)](https://travis-ci.org/prewk/xml-string-streamer-guzzle)
==========================

Use with [xml-string-streamer](https://github.com/prewk/xml-string-streamer)

What is it?
-----------

Streams large XML files with low memory consumption, over HTTP using [Guzzle](http://guzzlephp.org).

Installing
----------

composer.json:

````json
{
    "require": {
        "prewk/xml-string-streamer-guzzle": "~0.0.2"
    }
}
````


Examples
--------

````php
use Prewk\XmlStringStreamer;
use Prewk\XmlStringStreamer\StreamProvider; 

$url = "http://example.com/really-large-xml-file.xml";

$CHUNK_SIZE = 1024;
$streamProvider = new StreamProvider\Guzzle($url, $CHUNK_SIZE);

$streamer = new XmlStringStreamer\Parser($streamProvider);

while ($node = $streamer->getNode()) {
	// ...
}
````

For more info, see the [xml-string-streamer](https://github.com/prewk/xml-string-streamer) repo.
