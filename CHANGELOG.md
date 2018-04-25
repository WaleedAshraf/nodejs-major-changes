Jump to
- <a href="#6.0.0">6.0.0</a><br/>
- <a href="#6.0.0">8.0.0</a><br/>
- <a href="#6.0.0">9.0.0</a><br/>
- <a href="#6.0.0">10.0.0</a><br/>



<a id="6.0.0"></a>
## Version 6.0.0

The following significant changes have been made since the previous Node.js
v5.0.0 release.

* Buffer
  * New Buffer constructors have been added
    [#4682](https://github.com/nodejs/node/pull/4682) and
    [#5833](https://github.com/nodejs/node/pull/5833).
  * Existing `Buffer()` and `SlowBuffer()` constructors have been deprecated
    in docs [#4682](https://github.com/nodejs/node/pull/4682) and
    [#5833](https://github.com/nodejs/node/pull/5833).
  * Previously deprecated Buffer APIs are removed
    [#5048](https://github.com/nodejs/node/pull/5048),
    [#4594](https://github.com/nodejs/node/pull/4594).
  * Improved error handling [#4514](https://github.com/nodejs/node/pull/4514).
  * The `Buffer.prototype.lastIndexOf()` method has been added
    [#4846](https://github.com/nodejs/node/pull/4846).
* Cluster
  * Worker emitted as first argument in 'message' event
    [#5361](https://github.com/nodejs/node/pull/5361).
  * The `worker.exitedAfterDisconnect` property replaces `worker.suicide`
    [#3743](https://github.com/nodejs/node/pull/3743).
* Console
  * Calling `console.timeEnd()` with an unknown label now emits a process
    warning rather than throwing
    [#5901](https://github.com/nodejs/node/pull/5901).
* Crypto
  * Improved error handling [#3100](https://github.com/nodejs/node/pull/3100),
    [#5611](https://github.com/nodejs/node/pull/5611).
  * Simplified Certificate class bindings
    [#5382](https://github.com/nodejs/node/pull/5382).
  * Improved control over FIPS mode
    [#5181](https://github.com/nodejs/node/pull/5181).
  * pbkdf2 digest overloading is deprecated
    [#4047](https://github.com/nodejs/node/pull/4047).
* Dependencies
  * Reintroduce shared c-ares build support
    [#5775](https://github.com/nodejs/node/pull/5775).
  * V8 updated to 5.0.71.35 [#6372](https://github.com/nodejs/node/pull/6372).
* DNS
  * Add `dns.resolvePtr()` API to query plain DNS PTR records
    [#4921](https://github.com/nodejs/node/pull/4921).
* Domains
  * Clear stack when no error handler
  [#4659](https://github.com/nodejs/node/pull/4659).
* Events
  * The `EventEmitter.prototype._events` object no longer inherits from
    Object.prototype [#6092](https://github.com/nodejs/node/pull/6092).
  * The `EventEmitter.prototype.prependListener()` and
    `EventEmitter.prototype.prependOnceListener()` methods have been added
    [#6032](https://github.com/nodejs/node/pull/6032).
* File System
  * The `fs.realpath()` and `fs.realpathSync()` methods have been updated
    to use a more efficient libuv-based implementation. This change includes
    the removal of the `cache` argument and the method can throw new errors
    [#3594](https://github.com/nodejs/node/pull/3594).
  * FS apis can now accept and return paths as Buffers
    [#5616](https://github.com/nodejs/node/pull/5616).
  * Error handling and type checking improvements
    [#5616](https://github.com/nodejs/node/pull/5616),
    [#5590](https://github.com/nodejs/node/pull/5590),
    [#4518](https://github.com/nodejs/node/pull/4518),
    [#3917](https://github.com/nodejs/node/pull/3917).
  * fs.read's string interface is deprecated
    [#4525](https://github.com/nodejs/node/pull/4525).
* HTTP
  * 'clientError' can now be used to return custom errors from an
    HTTP server [#4557](https://github.com/nodejs/node/pull/4557).
* Modules
  * Current directory is now prioritized for local lookups
    [#5689](https://github.com/nodejs/node/pull/5689).
  * Symbolic links are preserved when requiring modules
    [#5950](https://github.com/nodejs/node/pull/5950).
* Net
  * DNS hints no longer implicitly set
    [#6021](https://github.com/nodejs/node/pull/6021).
  * Improved error handling and type checking
    [#5981](https://github.com/nodejs/node/pull/5981),
    [#5733](https://github.com/nodejs/node/pull/5733),
    [#2904](https://github.com/nodejs/node/pull/2904).
* npm
  * Running npm requires the node binary to be in the path
    [#6098](https://github.com/nodejs/node/pull/6098).
* OS X
  * MACOSX_DEPLOYMENT_TARGET has been bumped up to 10.7
    [#6402](https://github.com/nodejs/node/pull/6402).
* Path
  * Improved type checking [#5348](https://github.com/nodejs/node/pull/5348).
* Process
  * Introduce process warnings API
    [#4782](https://github.com/nodejs/node/pull/4782).
  * Throw exception when non-function passed to nextTick
    [#3860](https://github.com/nodejs/node/pull/3860).
* Querystring
  * The object returned by `querystring.parse()` no longer inherits from
    Object.prototype [#6055](https://github.com/nodejs/node/pull/6055).
* Readline
  * Key info is emitted unconditionally
    [#6024](https://github.com/nodejs/node/pull/6024).
  * History can now be explicitly disabled
    [#6352](https://github.com/nodejs/node/pull/6352).
* REPL
  * Assignment to `_` will emit a warning
    [#5535](https://github.com/nodejs/node/pull/5535).
  * Expressions will no longer be completed when eval fails
    [#6328](https://github.com/nodejs/node/pull/6328).
* Timers
  * Fail early when callback is not a function
    [#4362](https://github.com/nodejs/node/pull/4362).
* Streams
  * `null` is now an invalid chunk to write in object mode
    [#6170](https://github.com/nodejs/node/pull/6170).
* TLS
  * Rename 'clientError' to 'tlsClientError'
    [#4557](https://github.com/nodejs/node/pull/4557).
  * SHA1 used for sessionIdContext
    [#3866](https://github.com/nodejs/node/pull/3866).
* TTY
  * Previously deprecated setRawMode wrapper is removed
    [#2528](https://github.com/nodejs/node/pull/2528).
* URL
  * Username and password will be dropped by `url.resolve()` if the host
    changes [#1480](https://github.com/nodejs/node/pull/1480).
* Util
  * Changes to Error object formatting
    [#4582](https://github.com/nodejs/node/pull/4582).
  * The `util._extend()` method has been deprecated
    [#4903](https://github.com/nodejs/node/pull/4903)
  * The `util.log()` method has been deprecated
    [#6161](https://github.com/nodejs/node/pull/6161).
* Windows
  * Windows XP and Vista are no longer supported
    [#5167](https://github.com/nodejs/node/pull/5167).
* Zlib
  * Multiple improvements have been made to Zlib processing
    [#5883](https://github.com/nodejs/node/pull/5883) and
    [#5707](https://github.com/nodejs/node/pull/5707).
