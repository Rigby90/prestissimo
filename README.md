prestissimo (composer plugin)
=================================

[![Latest Stable Version](https://poser.pugx.org/hirak/prestissimo/v/stable)](https://packagist.org/packages/hirak/prestissimo) [![Total Downloads](https://poser.pugx.org/hirak/prestissimo/downloads)](https://packagist.org/packages/hirak/prestissimo) [![Latest Unstable Version](https://poser.pugx.org/hirak/prestissimo/v/unstable)](https://packagist.org/packages/hirak/prestissimo) [![License](https://poser.pugx.org/hirak/prestissimo/license)](https://packagist.org/packages/hirak/prestissimo)

[composer](https://getcomposer.org) parallel install plugin.

## Depends

- composer `>=1.0.0-alpha10` (includes dev-master)
- PHP `>=5.3`, (suggest `>=5.5`, because `curl_share_init`)
- ext-curl

## Install

```bash
$ composer global require hirak/prestissimo
```

## Uninstall

```bash
$ composer global remove hirak/prestissimo
```

## Config (optional)

in local composer.json

```
{
  ...
  "config": {
    "prestissimo": {
      "maxConnections": 6,
      "minConnections": 3,
      "pipeline": false,
      "verbose": false,
      "privatePackages": [
        "myorg/private1", "myorg/private2", ...
      ]
    }
  }
  ...
}
```

### maxConnections (int)
* default: 6

Limit connections for parallel downloading.

### minConnections (int)
* default: 3

If the number of packages is less than(`<=`) `minConnections`, prestissimo try to download by single connection.


### pipeline (bool)
* default: false

HTTP/1.1 pipelining option. It needs PHP `>=5.5`.

### verbose (bool)
* default: false

`CURLOPT_VERBOSE` option.

### privatePackages (string[])
* default: empty

If you list packages in this option, the local redirector(api.github.com -> codeload.github.com) will be off.

## License

MIT License. See the LICENSE file.
