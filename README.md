# README

Simple, Pythonic remote execution and deployment

## Installation

Copy `bin/fab` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl --location --output /usr/local/bin/fab "https://github.com/timonier/fabric/raw/master/bin/fab"
sudo chmod +x /usr/local/bin/fab
```

Linux users can use the [installer](https://github.com/timonier/fabric/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/fabric/raw/master/bin/installer" | sudo sh -s -- install
```

## Usage

Run the command `fab`:

```sh
# See all fab options

fab --help

# Run fab

$ fab --host 192.168.0.1 main
# [172.17.0.2] Executing task 'main'
# [172.17.0.2] sudo: DEBIAN_FRONTEND=noninteractive apt-get update --quiet
# [172.17.0.2] Login password for 'morgan':
# [172.17.0.2] out: sudo password:
# [172.17.0.2] out: Hit https://apt.dockerproject.org debian-jessie InRelease
# [172.17.0.2] out: Ign http://httpredir.debian.org jessie InRelease
# [172.17.0.2] out: Hit http://httpredir.debian.org jessie-updates InRelease
# [172.17.0.2] out: Get:1 https://apt.dockerproject.org debian-jessie/main amd64 Packages [4708 B]
# [172.17.0.2] out: Hit http://httpredir.debian.org jessie Release.gpg
# [172.17.0.2] out: Hit http://httpredir.debian.org jessie Release
# [172.17.0.2] out: Get:2 http://httpredir.debian.org jessie/main amd64 Packages [9032 kB]
# [172.17.0.2] out: Get:3 http://httpredir.debian.org jessie-updates/main amd64 Packages [17.6 kB]
# [172.17.0.2] out: Hit http://security.debian.org jessie/updates InRelease
# [172.17.0.2] out: Get:4 http://security.debian.org jessie/updates/main amd64 Packages [360 kB]
# [172.17.0.2] out: Fetched 9414 kB in 5s (1639 kB/s)
# [172.17.0.2] out: Reading package lists...
# [172.17.0.2] out:
# ...
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [fabric/fabric](https://github.com/fabric/fabric)
* [image "timonier/fabric"](https://hub.docker.com/r/timonier/fabric/)
* [sebastien/cuisine](https://github.com/sebastien/cuisine)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
