## Background

For Java backend engineer, a server means a running Java web-application process.
What is the equivalent in PHP world?

## PHP is scripting

PHP is not a web-server.
It is more like a scripting engine.
So, a web server (usually Apache) will start the PHP engine to interpret the scripts.

And yes, it will start and teardown the process once the requests has been served.

## Reference

* [Stackoverflow on How PHP works](https://stackoverflow.com/a/24797680/851118)