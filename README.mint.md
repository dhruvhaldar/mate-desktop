# Build Instructions for Linux Mint

These instructions will help you build and install `mate-desktop` on Linux Mint.

## Prerequisites

Open a terminal and install the required build dependencies:

```bash
sudo apt update
sudo apt install \
    autopoint \
    clang \
    clang-tools \
    git \
    gobject-introspection \
    gtk-doc-tools \
    intltool \
    iso-codes \
    libdconf-dev \
    libgirepository1.0-dev \
    libglib2.0-dev \
    libglib2.0-doc \
    libgtk-3-dev \
    libgtk-3-doc \
    libstartup-notification0-dev \
    libx11-dev \
    libxml2-dev \
    libxrandr-dev \
    mate-common \
    meson
```

## Building from Source

1.  **Clone the repository** (if you haven't already):
    ```bash
    git clone https://github.com/mate-desktop/mate-desktop.git
    cd mate-desktop
    ```

2.  **Prepare the build system**:
    ```bash
    ./autogen.sh
    ```

3.  **Compile the code**:
    ```bash
    make
    ```

4.  **Install**:
    ```bash
    sudo make install
    ```

## Uninstallation

To remove the installed files:

```bash
sudo make uninstall
```
