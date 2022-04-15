## Background

Coming from Java background which has a persistent server process, I'm wondering where is the counterpart in PHP.

## PHP is scripting

PHP is not a web-server.
It is more like a scripting engine.
So, a web server (usually Apache) will start the PHP engine to interpret the scripts.

And yes, it will start and teardown the process once the requests has been served.

## Reference

* [Stackoverflow on How PHP works](https://stackoverflow.com/a/24797680/851118)