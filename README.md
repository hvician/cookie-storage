# cookie-storage

A Web Storage interface for Cookie.

# Installation

```
$ npm install cookie-storage
```

# Usage

```javascript
import { CookieStorage } from 'cookie-storage';

const cookieStorage = new CookieStorage();

// Web Storage interface
cookieStorage.length === 0;

cookieStorage.setItem('key', 'value');
cookieStorage.length === 1;
cookieStorage.key(0) === 'key';

cookieStorage.getItem('key') === 'value';
cookieStorage.removeItem('key');
cookieStorage.length === 0;

cookieStorage.setItem('k1', 'v1');
cookieStorage.setItem('k2', 'v2');
cookieStorage.length === 2;

cookieStorage.clear();
cookieStorage.length === 0;

// Cookie options
cookieStorage.setItem('key', 'value', {
  path: '/',
  domain: 'example.com',
  expires: new Date(),
  secure: true
});

// Use default cookie options
const storage = new CookieStorage({
  path: '/',
  domain: 'example.com',
  expires: new Date(),
  secure: true
});
storage.setItem('key', 'value'); // ;path=/;domain=example.com;...
```

# Development

```
$ npm install
$ npm run watch
```

## License

[MIT](LICENSE)

## Author

[bouzuya][user] &lt;[m@bouzuya.net][email]&gt; ([http://bouzuya.net][url])

## Status

[![Build Status][travis-badge]][travis]

[user]: https://github.com/bouzuya
[email]: mailto:m@bouzuya.net
[url]: http://bouzuya.net
[travis]: https://travis-ci.org/bouzuya/cookie-storage
[travis-badge]: https://travis-ci.org/bouzuya/cookie-storage.svg?branch=master
