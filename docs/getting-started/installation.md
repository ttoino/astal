# Installation

## Nix

maintainer: [@Aylur](https://github.com/Aylur)

Read more about it on the [nix page](./nix)

## Arch

maintainer: [@kotontrion](https://github.com/kotontrion)

:::code-group

```sh [Core Library]
yay -S libastal-git
```

```sh [Every Library]
yay -S libastal-meta
```

:::

## Bulding libastal from source

1. Clone the repo

```sh
git clone https://github.com/aylur/astal.git
cd astal/core
```

2. Install the following dependencies

:::code-group

```sh [Arch]
sudo pacman -Syu meson vala gtk3 gtk-layer-shell gobject-introspection
```

```sh [Fedora]
sudo dnf install meson gcc valac gtk3-devel gtk-layer-shell-devel
```

```sh [Alpine]
sudo apk add meson g++ vala gtk+3.0-dev gtk-layer-shell-dev gobject-introspection-dev
```

```sh [Ubuntu]
sudo apt install meson valac libgtk3-dev libgtk-layer-shell-dev gobject-introspection
```

```sh [openSUSE]
sudo zypper install gcc meson vala gtk3-devel gtk-layer-shell-devel gobject-introspection-devel
```

:::

3. Build and install with `meson`

```sh
meson setup build
meson install -C build
```

:::info
Most distros recommend manual installs in `/usr/local`,
which is what `meson` defaults to. If you want to install to `/usr`
instead which most package managers do, set the `prefix` option:

```sh
meson setup --prefix /usr build
meson install -C build
```

:::