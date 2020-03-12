# [risk3sixty](https://risk3sixty.com)

## geoapi

Tiny API service to report geolocation data from IP addresses.
The underlying data is coming from [geoip-lite](https://www.npmjs.com/package/geoip-lite)
so special thanks to the contributors of this package and
[MaxMind](https://maxmind.com) for keeping up-to-date information
in the geolocation DB!

### Usage

Make a GET request to the geoapi endpoint with `/me` or an IP
address (IPv4 or IPv6) located in the path of the URL, e.g.
`https://geo.risk3sixty.com/8.8.8.8`. The server responds with JSON
that contains geolocation data present for the provided IP address,
or your current IP address if `/me` was passed.

Also, [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
is enabled for browser usage.

```sh
# https://geo.risk3sixty.com/IPV4_OR_IPV6_IP_ADDRESS

$ curl https://geo.risk3sixty.com/me
{"ip":"196.245.163.202","range":[3304431616,3304432639],"country":"GB","region":"ENG","eu":"1","timezone":"Europe/London","city":"London","ll":[51.5064,-0.02],"metro":0,"area":50}

$ curl https://geo.risk3sixty.com/128.61.0.0
{"ip":"128.61.0.0","range":[2151481344,2151546879],"country":"US","region":"GA","eu":"0","timezone":"America/New_York","city":"Atlanta","ll":[33.7746,-84.3973],"metro":524,"area":5}

$ curl https://geo.risk3sixty.com/2001:468:300:0:0:0:0:0
{"ip":"2001:468:300:0:0:0:0:0","range":"","country":"US","region":"","city":"","ll":[37.751,-97.822],"metro":0,"area":100,"eu":"0","timezone":"America/Chicago"}
```

### Development

```sh
$ git clone https://github.com/Risk3sixty-Labs/geoapi
$ cd geoapi
$ npm install

# run tests
$ npm test

# build production files
$ npm run build

# start server
$ npm start
```

### License

MIT