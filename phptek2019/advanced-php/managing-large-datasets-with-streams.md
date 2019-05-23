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
    * `stream_get_transports()` returns the list 
    * tcp,udp,unix,udg,ssl,tls,tlsv1.0,tlsv1.1,tlsv1.2 
* Stream Wrappers
    * `stream_get_wrappers()`
    * https,ftps,compress.zlib,compress.bzip2,php,file,glob,data,http,ftp,phar,zip
* Stream Filters
    * `stream_get_filters()`
    * `zlib.*,bzip2.*,convert.iconv.*,mcrypt.*,mdecrypt.*,string.rot13,string.toupper,string.tolower,string.strip_tags,convert.*,consumed,dechunk`
* Stream Context
    ```
    $context = [
        'http' => [
            'headers' => '.....'
        ...
        ]
    ];
    stream_context_set_default($context);
    file_get_contents('http://whatever');
    ```
* Size matters
    * Consume too much and you get Fatal OOM
    * `ini_set('memory_limit', ...)` is a workaround, but has major limitations obviously
    * Instead, use streams
*  
      