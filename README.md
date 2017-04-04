# api documentation for  [ratelimiter (v3.0.3)](https://github.com/visionmedia/node-ratelimiter#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-ratelimiter.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-ratelimiter) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-ratelimiter.svg)](https://travis-ci.org/npmdoc/node-npmdoc-ratelimiter)
#### abstract rate limiter backed by redis

[![NPM](https://nodei.co/npm/ratelimiter.png?downloads=true)](https://www.npmjs.com/package/ratelimiter)

[![apidoc](https://npmdoc.github.io/node-npmdoc-ratelimiter/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-ratelimiter_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-ratelimiter/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-ratelimiter/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-ratelimiter/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/visionmedia/node-ratelimiter/issues"
    },
    "contributors": [
        {
            "name": "Francois-Guillaume Ribreau",
            "email": "npm@fgribreau.com"
        }
    ],
    "dependencies": {},
    "description": "abstract rate limiter backed by redis",
    "devDependencies": {
        "async": "2.1.4",
        "ioredis": "1.15.1",
        "mocha": "*",
        "redis": "2.6.0-1",
        "should": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "6dbca58b05422f2a08e224d4ba3a0cfb86c30966",
        "tarball": "https://registry.npmjs.org/ratelimiter/-/ratelimiter-3.0.3.tgz"
    },
    "gitHead": "9a0ce10dee614e44e2f3127ce68a65cab9381753",
    "homepage": "https://github.com/visionmedia/node-ratelimiter#readme",
    "keywords": [
        "rate",
        "ratelimit",
        "limiter",
        "limit"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "tjholowaychuk",
            "email": "tj@vision-media.ca"
        },
        {
            "name": "noamshemesh",
            "email": "noamshemesh@gmail.com"
        }
    ],
    "name": "ratelimiter",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/visionmedia/node-ratelimiter.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "3.0.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module ratelimiter](#apidoc.module.ratelimiter)
1.  object <span class="apidocSignatureSpan">ratelimiter.</span>microtime

#### [module ratelimiter.microtime](#apidoc.module.ratelimiter.microtime)
1.  [function <span class="apidocSignatureSpan">ratelimiter.microtime.</span>now ()](#apidoc.element.ratelimiter.microtime.now)



# <a name="apidoc.module.ratelimiter"></a>[module ratelimiter](#apidoc.module.ratelimiter)



# <a name="apidoc.module.ratelimiter.microtime"></a>[module ratelimiter.microtime](#apidoc.module.ratelimiter.microtime)

#### <a name="apidoc.element.ratelimiter.microtime.now"></a>[function <span class="apidocSignatureSpan">ratelimiter.microtime.</span>now ()](#apidoc.element.ratelimiter.microtime.now)
- description and source-code
```javascript
now = function () {
  var diff = process.hrtime(start);

  return time + diff[0] * 1e6 + Math.round(diff[1] * 1e-3);
}
```
- example usage
```shell
...
  res.set('X-RateLimit-Reset', limit.reset);

  // all good
  debug('remaining %s/%s %s', limit.remaining - 1, limit.total, id);
  if (limit.remaining) return next();

  // not good
  var delta = (limit.reset * 1000) - Date.now() | 0;
  var after = limit.reset - (Date.now() / 1000) | 0;
  res.set('Retry-After', after);
  res.send(429, 'Rate limit exceeded, retry in ' + ms(delta, { long: true }));
});
'''

## Result Object
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
