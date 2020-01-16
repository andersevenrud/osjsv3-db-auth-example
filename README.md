<p align="center">
  <img alt="OS.js Logo" src="https://raw.githubusercontent.com/os-js/gfx/master/logo-big.png" />
</p>

# OS.js v3 Database Auth Docker Example

This example runs on docker and demonstrates the database authentication adapter.

[![Support](https://img.shields.io/badge/patreon-support-orange.svg)](https://www.patreon.com/user?u=2978551&ty=h&u=2978551)
[![Back](https://opencollective.com/osjs/tiers/backer/badge.svg?label=backer&color=brightgreen)](https://opencollective.com/osjs)
[![Sponsor](https://opencollective.com/osjs/tiers/sponsor/badge.svg?label=sponsor&color=brightgreen)](https://opencollective.com/osjs)
[![Donate](https://img.shields.io/badge/liberapay-donate-yellowgreen.svg)](https://liberapay.com/os-js/)
[![Donate](https://img.shields.io/badge/paypal-donate-yellow.svg)](https://paypal.me/andersevenrud)
[![Community](https://img.shields.io/badge/join-community-green.svg)](https://community.os-js.org/)

## Installation

Uses the official distribution template and runs on http://localhost:8000 by default.

### Setup

After the first time you've run this setup procedure you can simply use `docker-compose up` and skip the steps below.

#### Database

First set up database:

```bash
docker-compose up db
```

```bash
echo "CREATE DATABASE osjsv3;" | docker-compose exec db mysql -uroot -psecret
echo "CREATE USER 'osjsv3'@'localhost' IDENTIFIED BY 'secret';" | docker-compose exec db mysql -uroot -psecret
echo "GRANT ALL ON osjsv3.* TO 'osjsv3'@'localhost';" | docker-compose exec db mysql -uroot -psecret
```

#### Instance

Then start OS.js:

> Note that the first time this is run it might take a while.

```bash
docker-compose up
```

#### Add users

Now you can add users (you will get prompted for a password):

```bash
docker-compose exec osjs npx osjs-cli user:add --username=name --groups=admin
```

## Contribution

* **Become a [Patreon](https://www.patreon.com/user?u=2978551&ty=h&u=2978551)**
* **Support on [Open Collective](https://opencollective.com/osjs)**
* [Contribution Guide](https://github.com/os-js/OS.js/blob/v3/CONTRIBUTING.md)

## Documentation

See the [Official Manuals](https://manual.os-js.org/v3/) for articles, tutorials and guides.

## Links

* [Official Chat](https://gitter.im/os-js/OS.js)
* [Community Forums and Announcements](https://community.os-js.org/)
* [Homepage](https://os-js.org/)
* [Twitter](https://twitter.com/osjsorg) ([author](https://twitter.com/andersevenrud))
* [Google+](https://plus.google.com/b/113399210633478618934/113399210633478618934)
* [Facebook](https://www.facebook.com/os.js.org)
* [Docker Hub](https://hub.docker.com/u/osjs/)
