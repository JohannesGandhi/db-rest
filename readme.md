# db-rest

**A clean REST API wrapping around the [Deutsche Bahn HAFAS API](https://github.com/public-transport/db-hafas#db-hafas).** It is deployed at [`v6.db.transport.rest`](https://v6.db.transport.rest/).

[**API Documentation**](docs/readme.md)

![db-rest architecture diagram](architecture.svg)

[![API status](https://badgen.net/uptime-robot/status/m793274556-25c5e9bbab0297d91cda7134)](https://stats.uptimerobot.com/57wNLs39M/793274556)
[![dependency status](https://img.shields.io/david/derhuerst/db-rest.svg)](https://david-dm.org/derhuerst/db-rest)
![ISC-licensed](https://img.shields.io/github/license/derhuerst/db-rest.svg)
[![support me via GitHub Sponsors](https://img.shields.io/badge/support%20me-donate-fa7664.svg)](https://github.com/sponsors/derhuerst)
[![chat with me on Twitter](https://img.shields.io/badge/chat%20with%20me-on%20Twitter-1da1f2.svg)](https://twitter.com/derhuerst)


## installing & running

### access to Redis

It is recommended that you let `bvg-rest` cache HAFAS responses within a [Redis](https://redis.io/) cache. To use this feature, set `$REDIS_URL` (e.g. to `redis://localhost:6379/1` when running Redis locally).

### via Docker

A Docker image [is available as `docker.io/derhuerst/db-rest:6`](https://hub.docker.com/r/docker.io/derhuerst/db-rest:6).

```shell
docker run -d -p 3000:3000 docker.io/derhuerst/db-rest:6
```

*Note:* The Docker image does not contain the Redis server.

### manually

```shell
git clone https://github.com/derhuerst/db-rest.git
cd db-rest
git checkout 6
npm install

export HOSTNAME='my-vbb-rest-api.example.org'
npm run build

redis-server &
npm start
```

To keep the API running permanently, use tools like [`forever`](https://github.com/foreverjs/forever#forever) or [`systemd`](https://wiki.debian.org/systemd).


## Related Projects

- [`DB-Adapter-v6`](https://github.com/olech2412/DB-Adapter-v6) – A Java API client for `db-rest`.
- [`vbb-rest`](https://github.com/derhuerst/vbb-rest) – A clean REST API wrapping around the VBB API.
- [`bvg-rest`](https://github.com/derhuerst/bvg-rest) – A clean REST API wrapping around the BVG API.
- [`hvv-rest`](https://github.com/derhuerst/hvv-rest) – A clean REST API wrapping around the HVV API.
- [`hafas-rest-api`](https://github.com/public-transport/hafas-rest-api) – Expose a HAFAS client via an HTTP REST API.
- [`hafas-client`](https://github.com/public-transport/hafas-client) – JavaScript client for HAFAS public transport APIs.


## Contributing

If you **have a question**, **found a bug** or want to **propose a feature**, have a look at [the issues page](https://github.com/derhuerst/db-rest/issues).
