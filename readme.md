*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-bmp](http://github.com/sindresorhus/is-bmp). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-bmp`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-bmp [![Build Status](https://travis-ci.org/sindresorhus/is-bmp.svg?branch=master)](https://travis-ci.org/sindresorhus/is-bmp)

> Check if a Buffer/Uint8Array is a [BMP](http://en.wikipedia.org/wiki/BMP_file_format) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-bmp
```

```sh
$ bower install --save is-bmp
```

```sh
$ component install sindresorhus/is-bmp
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isBmp = require('is-bmp');
var buffer = readChunk('unicorn.bmp', 0, 2);

isBmp(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.bmp');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isBmp(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isBmp(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 2 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
