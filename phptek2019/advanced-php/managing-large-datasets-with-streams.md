# Managing Large Datasets with Streams

Joe Ferguson

* What is a stream?
    * A stream is a resource objects which exhibits streamable behavior ~ phpdocs
    * typically a file pointer, but could be many different things. 
    * Any data that has the ability to seek and rewind. (Linear data)
* Streams look like: `scheme://target`. You don't use streams directly, you use a wrapper.
    * File streams: path to file
    * Network streams: host/path
* `file()`, `open()`, `fwrite()`, `fclose()`, `file_get_contents()`, `file_put_contents()` all deal with streams under the hood
* Stream Transports
    * `stream_get_transports()` returns the list e.g. tcp, udp, unix, 
* Stream Wrappers
    * https,ftps,compress.zlib,compress.bzip2,php,file,glob,data,http,ftp,phar,zip
