# DEPRECATED: These Dockerfiles will be superseded with userspace runc configs.

# Docker apps based from archlinux

The Dockerfiles in this repository were ported from [jessfraz/dockerfiles](https://github.com/jessfraz/dockerfiles). Her Dockerfiles are based on other distros but she has a ton of them, so look there for additional apps.

## Requirements

  * Docker
  * xorg-xhost (for GUI apps)

## Building the base image

  1. `cd archlinux/`
  2. `docker build --tag local/archlinux .`

Packages can be updated without rebuilding the entire image by setting `BUST_CACHE` on `docker build`:
```sh
docker build --build-arg "BUST_CACHE=$(date --iso-8601=s)" --tag local/archlinux .
```

## Building an app image

  1. `cd` into the directory of the app you want to build.
  2. Run `docker build --tag "local/$app" .`.

## Running an app

  1. Launch the app with the provided executable.

### GTK styles

Apps can be launched with window decorations matching the host system by mounting the correct GTK configuration.

#### GTK2

Mount `$HOME/.gtkrc-2.0` into the container.

```
docker run \
  --volume $HOME/.gtkrc-2.0:/home/arch/.gtkrc-2.0:ro \
  # ...
```

#### GTK3

Mount `$HOME/.config/gtkrc-3.0` into the container.

```
docker run \
  --volume $HOME/.config/gtk-3.0:/home/arch/.config/gtk-3.0 \
  # ...
```

## License

Public Domain
