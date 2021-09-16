# Check PHP Information

1. Check PHP version
    ```bash
    $ php -v

    PHP 7.2.10 (cli) (built: Sep 13 2018 00:48:27) ( ZTS MSVC15 (Visual C++ 2017) x64 )
    Copyright (c) 1997-2018 The PHP Group
    Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
    ```

1. Check current `php.ini` location
    ```bash
    $ php --ini

    Configuration File (php.ini) Path: C:\WINDOWS
    Loaded Configuration File:         C:\wamp64\bin\php\php7.2.10\php.ini
    Scan for additional .ini files in: (none)
    Additional .ini files parsed:      (none)
    ```

1. Check current PHP environment variable path
    ```bash
    $ which php

    /c/wamp64/bin/php/php7.2.10/php
    ```

1. View current active PHP modules
    ```bash
    $ php -r "print_r(get_loaded_extensions());"
    $ php -m

    [PHP Modules]
    bcmath
    bz2
    calendar
    .
    .
    .
    xsl
    zip
    zlib

    [Zend Modules]
    ```

1. View more detailed information on what the current configuration
    ```bash
    $ php -i
    ```

1. View installed extentions
    ```bash
    php -r "print_r(get_loaded_extensions());"
    ```
