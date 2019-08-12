# Configuring xdebug for php7.x with xampp

## Requirements

* XAMPP for Windows: https://www.apachefriends.org/download.html
* The VC14 build requires Visual C++ Redistributable for Visual Studio 2015 [x86 or x64](http://www.microsoft.com/en-us/download/details.aspx?id=48145) to be installed.
* The VC15 build requires: Visual C++ Redistributable for Visual Studio 2017 x64 or [x86](https://go.microsoft.com/fwlink/?LinkId=746571) to be installed.

## Setup

* Download Xdebug for the specific PHP version:

  * PHP 7.0: https://xdebug.org/files/php_xdebug-2.6.1-7.0-vc14.dll
  * PHP 7.1: https://xdebug.org/files/php_xdebug-2.7.2-7.1-vc14.dll
  * PHP 7.2: https://xdebug.org/files/php_xdebug-2.7.2-7.2-vc15.dll
  * PHP 7.3: https://xdebug.org/files/php_xdebug-2.7.2-7.3-vc15.dll
  
* Copy the dll file `php_xdebug-2.7.2-7.3-vc15.dll` to: `C:\xampp\php\ext`

* Open the file `C:\xampp\php\php.ini` with Notepad++

* Disable output buffering: `output_buffering = Off`

* Scroll down to the `[XDebug]` section (or create it) and copy/paste these lines:

```ini
[XDebug]
zend_extension = "c:\xampp\php\ext\php_xdebug-2.7.1-7.3-vc15.dll"
xdebug.remote_autostart = 1
xdebug.profiler_append = 0
xdebug.profiler_enable = 0
xdebug.profiler_enable_trigger = 0
xdebug.profiler_output_dir = "c:\xampp\tmp"
;xdebug.profiler_output_name = "cachegrind.out.%t-%s"
xdebug.remote_enable = 1
xdebug.remote_handler = "dbgp"
xdebug.remote_host = "127.0.0.1"
xdebug.remote_log = "c:\xampp\tmp\xdebug.txt"
xdebug.remote_port = 9000
xdebug.trace_output_dir = "c:\xampp\tmp"
;36000 = 10h
xdebug.remote_cookie_expire_time = 36000
```

* Restart Apache

* Click the Github &#9733; Star button :-)

## PhpStorm

* Use the [PhpStorm bookmarklets generator](https://www.jetbrains.com/phpstorm/marklets/) to activate Xdebug from the browser side.

## Netbeans

* Change the Netbeans debugging options: https://user-images.githubusercontent.com/781074/39868196-c98f15a0-5458-11e8-8143-d8c44079e099.jpg

## Eclipse

* No comment

## Visual Studio Code

* Install the [PHP Debug Adapter for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug).
* [Debug PHP In VSCode With XDebug](https://www.codewall.co.uk/debug-php-in-vscode-with-xdebug/)

## Adobe Brackets

* Install the [PHP Debugger for Brackets](https://github.com/spocke/php-debugger).

## Sublime Text 2 and 3

* Install the [Xdebug Client Package](https://packagecontrol.io/packages/Xdebug%20Client)
