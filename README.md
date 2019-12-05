# h2buster (v0.4c) #
A fast, threaded, recursive, web directory brute-force scanner over HTTP/2 using [hyper](https://github.com/Lukasa/hyper), inspired by [Gobuster](https://github.com/OJ/gobuster).

## Features ##
* Fast and portable - install [hyper](https://github.com/Lukasa/hyper) and run.
* Multiconnection scanning.
* Multithreaded connections.
* Scalable: scans can be as docile or aggressive as you configure them to be.
* h2 and h2c support.
* Configurable directory recursion depth.
* robots.txt scanning.
* Multiplatform: works on both \*nix and Windows.

## Install ##
Requires Python 3.6.
You only need to install one dependency. If you don't have [hyper](https://github.com/Lukasa/hyper), run:\
`pip3 install -r requirements.txt`

## Usage ##
```
usage: h2buster.py [-h] -w wordlist -u target [-c connections=4]
                   [-t threads=20] [-m http_method=HEAD]
                   [-r directory_depth=2] [-hd header_list]
                   [-x extension_list] [-b http_code_list] [-l] [-vr] [-rb]
                   [-nc]

h2buster: an HTTP/2 web directory brute-force scanner.

arguments:
  -h, --help            show this help message and exit
  -w wordlist           Directory wordlist
  -u target             Target URL/IP address ([scheme://]host[:port]).
                        Default port is 443 and HTTPS enabled. To specify
                        otherwise, use ':port' and/or 'http://' (port will
                        default to 80 then).
  -c connections=4      Number of HTTP/2 connections.
  -t threads=20         Number of threads per connection.
  -m http_method=HEAD   HTTP request method. Allowed values are GET, HEAD.
  -r directory_depth=2  Maximum recursive directory depth. Minimum is 1,
                        unlimited is 0.
  -hd header_list       List of headers in the format
                        'header->value|header->value...'. For example: -hd
                        'user-agent->Mozilla/5.0|accept-encoding->gzip,
                        deflate, br'.
  -x extension_list     List of file extensions to check separated by a
                        vertical bar (|). For example, -x '.php|.js|blank|/'.
                        The 'blank' keyword signifies no file extension.
                        Default extensions are '/', 'blank', '.html', '.php'
  -b http_code_list     List of blacklisted response codes separated by a
                        vertical bar (|). Directories with these response
                        codes will not be shown in the output. Default is 404.
  -l                    Flag: show response length in output. This overrides
                        the request method to GET.
  -vr                   Flag: force TLS certificate verification.
  -rb                   Flag: scan for a robots.txt file. If found, a prompt
                        will be displayed asking whether to use the results.
  -nc                   Flag: disable colored output text.
```

## Contributing ##
Check the [TODO](TODO.md) file for a list of features that need work.
