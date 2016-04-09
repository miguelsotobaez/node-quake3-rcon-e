# quake3-rcon

> A tiny library for Quake 3's RCON connection & server commands, including command-line interface.

`quake3-rcon` lets you send rcon commands to your Quake 3 server. You can use it as a library for your project or as an interface to access your server from your command-line.

## Install

Install this package globally with [NPM](https://www.npmjs.com/) to use the `command-line interface`. Most OS need you to be root (e.g. using `sudo`) to install a global npm package:

```sh
$ [sudo] npm -g install quake3-rcon
```

or install `quake3-rcon` as a dependency for your package:

```sh
$ npm install --save quake3-rcon
```

`quake3-rcon` depends on [Node.js](https://nodejs.org/). Tested with `node v4.3.0`.

## Usage: command-line interface

run:

```sh
$ quake3-rcon <server-address[:port]> <rcon-password>
```

and then type in your commands for the server, e.g. `say Hi` or `addbot Sarge`.

## API

```
var Q3RCon = require('quake3-rcon');
```

Initialize the `quake3-rcon` object:

```
var rcon = new Q3RCon('server:port', 'password');
```

Send a command to the server:

```
rcon.send('rcon_command param1 param2 ...', function(message) {
    // this callback is optional
});
```

### Example

```
var Q3RCon = require('quake3-rcon');

var rcon = new Q3RCon('127.0.0.1:27960', 'my_super_secret_password');

rcon.send('say Hello, World!', function(message) {
    console.log(message.toString('ascii').slice(4).trim());
});
```

That's it. Have fun.

## Support

Found a bug? Open an issue [here](https://github.com/thbaumbach/quake3-rcon/issues) on Github.

Wanna help? Submit a pull request or contact me.

Wanna tip me a beer? Use [Bitcoin](bitcoin:14pSD9AmuNhLDbGRXehxbhwzRSRrkpiAKg): 14pSD9AmuNhLDbGRXehxbhwzRSRrkpiAKg

## License

Copyright (c) 2016 Thomas Baumbach <tom@xolo.pw>

Licensed under the MIT License