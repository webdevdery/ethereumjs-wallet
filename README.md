# ethereumjs-wallet

A lightweight wallet implementation. At the moment it supports key creation and conversion between various formats.

It is complemented by the following packages:
- [ethereumjs-tx](https://github.com/ethereumjs/ethereumjs-tx) to sign transactions
- [ethereumjs-icap](https://github.com/ethereumjs/ethereumjs-icap) to manipulate ICAP addresses
- [store.js](https://github.com/marcuswestin/store.js) to use browser storage

Motivations are:
- be lightweight
- work in a browser
- use a single, maintained version of crypto library
- support import/export between various wallet formats

Features not supported:
- signing transactions
- managing storage (neither in node.js or the browser)

## API

Constructors:

* `fromPrivateKey(input)` - create an instance based on a raw key
* `fromV1(input, password)` - import a wallet (Version 1 of the Ethereum wallet format)
* `fromV3(input, password)` - import a wallet (Version 3 of the Ethereum wallet format)
* `fromEthSale(input, password)` - import an Ethereum Pre Sale wallet

For the V1, V3 and EthSale formats the input is a JSON serialized string. All these formats require a password.

Instance methods:

* `getPrivateKey()` - return the private key
* `getPublicKey()` - return the public key
* `getAddress()` - return the address
* `toV3(password, [options])` - return the wallet as a JSON string (Version 3 of the Ethereum wallet format)

All of the above instance methods return a Buffer or JSON. Use the `String` suffixed versions for a string output, such as `getPrivateKeyString()`.

### Remarks about `toV3`

The `options` is an optional object hash, where all the serialization parameters can be fine tuned:
- uuid - UUID. One is randomly generated.
- salt - Random salt for the `kdf`. Size must match the requirements of the KDF (key derivation function). Random number generated via `crypto.getRandomBytes` if nothing is supplied.
- iv - Initialization vector for the `cipher`. Size must match the requirements of the cipher. Random number generated via `crypto.getRandomBytes` if nothing is supplied.
- kdf - The key derivation function, see below.
- dklen - Derived key length. For certain `cipher` settings, this must match the block sizes of those.
- cipher - The cipher to use. Names must match those of supported by `OpenSSL`, e.g. `aes-128-ctr` or `aes-128-cbc`.

Depending on the `kdf` selected, the following options are available too.

For `pbkdf2`:
- `c` - Number of iterations. Defaults to 262144.
- `prf` - The only supported (and default) value is `hmac-sha256`. So no point changing it.

For `scrypt`:
- `n` - Iteration count. Defaults to 262144.
- `r` - Block size for the underlying hash. Defaults to 8.
- `p` - Parallelization factor. Defaults to 1.

The following settings are favoured by the Go Ethereum implementation and we default to the same:
- `kdf`: `scrypt`
- `dklen`: `32`
- `n`: `262144`
- `r`: `8`
- `p`: `1`
- `cipher`: `aes-128-ctr`
