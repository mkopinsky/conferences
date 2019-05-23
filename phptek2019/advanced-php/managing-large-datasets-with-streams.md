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
    ```php
    $context = [
        'http' => [
            'headers' => '.....',
            // ...
        ]
    ];
    stream_context_set_default($context);
    file_get_contents('http://whatever');
    ```
* Size matters
    * Consume too much and you get Fatal OOM
    * `ini_set('memory_limit', ...)` is a workaround, but has major limitations obviously
    * Instead, use streams
    ```php
    $handle = fopen(
        'http://releases.ubuntu.com/.../whatever.iso',
        'rb' // mode
    );
    $destination = fopen('./whatever.iso', 'w');
    stream_copy_to_stream($handle, $destination);
    ```
* Reading from pointers
    ```php
    $file = fopen('file.csv', 'r');

    while (!feof($file)) {
        $line = trim(fgets($file));
        
        if ('condition') {
            $people[] = str_getcsv($line);
        }
    }
    ```
    This only requires only as much RAM as the largest row in the file.
* Rewinding Stream
    * `ftell()` tells you how far into the file you are
    * `rewind($file)` goes back to the beginning
    * `fseek($file, 96);` goes forward by 96 bytes. (Can also go negative.)
    * These are all wrappers around 
* Guzzle
    * uses streams
    * Constructor is used to set context (like context above!) for request
    * Response is a `GuzzleHttps\Psr7\Stream`.
        * In Joe's example, it had ui of `php://temp` because it fetched the data and shoved it into a PHP temp file in memory
        * Cast to string to get response body
        * To use as streams
            * `$hundredBytes = $body->read(100);`
            * Once we have a sense it's safe, fetch and json_decode with `json_decode($response->getBody)`
* Audience questions
    * How do you seek on remote files?
        * Use streams to download, then seek on the local files
    *     



Side things:
* [Faker](https://github.com/fzaninotto/Faker) is a library to create random data
