# geolocationmock-go

This repository contains a simple quick 'n dirty mock server of the [https://ip-api.com/](https://ip-api.com/) and [https://ipbase.com/](https://ipbase.com/) IP geolocation API.

It is mostly used for the development and testing of [REST-go-k8s-geolocation](https://github.com/adavarski/REST-go-k8s-geolocation).

## Configuration and usage

`geolocationmock-go` is configurable with flags:

```
Usage of ./geolocationmock-go:
  -e2e
    	Enable 'e2e' mode: set fixed responses instead of random
  -failure int
    	Failure response rate
  -latency duration
    	Response request latency
  -provider string
    	Provier name. Available: 'ipapi', 'ipbase' (default "ipapi")
```

### Available flags

* `-provider` (default `ipapi`). Start a mock server of the given IP geolocation API. Available values are `ipapi` and `ipbase`.

* `-latency` (default `0s`). Inject given latency into the server response. Examples: `150ms`, `2s`, `1m`, ...

* `-failure` (default `0`). Inject given failure rate into the server response. Examples: `10` for 10%, `50` for 50%.

* `-e2e` (default `false`). If true, enable "e2e" mode where there is a fixed response for the routes `/ip/1.1.1.1`, `/ip/2.2.2.2` and `/ip/3.3.3.3` instead of a random one for the `ipbase` provider.
