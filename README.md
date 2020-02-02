# Vertex Theme

Vertex is a theme for GTK 3, GTK 2, Gnome-Shell and Cinnamon. It supports GTK 3 and GTK 2 based desktop environments like Gnome, Cinnamon, Mate, XFCE, Budgie, Pantheon, etc. Themes for the Browsers Chrome/Chromium and Firefox are included, too.

The theme comes with three variants to choose from. The default variant with dark header-bars, a light variant, and a dark variant.

### Requirements

* GNOME Shell 3.18 - 3.34, GTK 3.18 - 3.24
* The `gnome-themes-extra` package
* The murrine engine. This has different names depending on your distro.
  * `gtk-engine-murrine` (Arch Linux)
  * `gtk2-engines-murrine` (Debian, Ubuntu, elementary OS)
  * `gtk-murrine-engine` (Fedora)
  * `gtk2-engine-murrine` (openSUSE)
  * `gtk-engines-murrine` (Gentoo)

### Installation

**Important:** Remove all older versions of the theme from your system before you proceed any further.

    sudo rm -rf /usr/share/themes/{Vertex,Vertex-Dark,Vertex-Light,Vertex-Gnome-Shell,Gnome-Shell-3.16,Vertex-Cinnamon}
    rm -rf ~/.local/share/themes/{Vertex,Vertex-Dark,Vertex-Light,Vertex-Gnome-Shell,Gnome-Shell-3.16,Vertex-Cinnamon}
    rm -rf ~/.themes/{Vertex,Vertex-Dark,Vertex-Light,Vertex-Gnome-Shell,Gnome-Shell-3.16,Vertex-Cinnamon}

**Packages**

Prebuilt packages for Ubuntu, Debian, Fedora and openSUSE are available at

http://software.opensuse.org/download.html?project=home%3AHorst3180&package=vertex-theme

Arch Linux users can install the theme from the AUR

https://aur.archlinux.org/packages/vertex-themes

https://aur.archlinux.org/packages/vertex-themes-git/

**Manual Installation**

To build the theme you need
* `autoconf`
* `automake`
* `pkg-config` or `pkgconfig` if you use Fedora
* `libgtk-3-dev` for Debian based distros or `gtk3-devel` for RPM based distros, for auto-detecting the GTK3 version
* `git` if you want to clone the source directory

If your distributions doesn't ship separate development packages you just need GTK 3 instead of the `-dev` packages.

Install the theme with the following commands

**1. Get the source**

If you want to install the latest version from git, clone the repository with

    git clone https://github.com/horst3180/vertex-theme --depth 1 && cd vertex-theme

If you want to install the latest stable release, run

    git clone https://github.com/horst3180/vertex-theme --depth 1 && cd vertex-theme
    git fetch --tags
    git checkout $(git describe --tags `git rev-list --tags --max-count=1`)

or download it from https://github.com/horst3180/Vertex-theme/releases and cd into the extracted archive

**2. Build and install the theme**

    ./autogen.sh --prefix=/usr
    sudo make install

Other options to pass to autogen.sh are

    --disable-cinnamon             disable Cinnamon support
    --disable-dark                 disable Vertex Dark support
    --disable-gnome-shell          disable GNOME Shell support
    --disable-gtk2                 disable GTK2 support
    --disable-gtk3                 disable GTK3 support
    --disable-light                disable Vertex Light support
    --disable-metacity             disable Metacity support
    --disable-unity                disable Unity support
    --disable-xfwm                 disable XFWM support
    --disable-plank                disable Plank theme support

    --with-gnome-shell=<version>   build the gnome-shell theme for a specific version
    --with-gtk3=<version>          build the GTK3 theme for a specific version
                                   Note: Normally the correct version is detected automatically
                                   and these options should not be needed.

After the installation is complete you can activate the theme with `gnome-tweak-tool` or a similar program by selecting `Vertex`, `Vertex-Light` or `Vertex-Dark`.

**Uninstall the theme**

Run

    sudo make uninstall

from the same directory as this README resides in, or

    sudo rm -rf /usr/share/themes/{Vertex,Vertex-Dark,Vertex-Light}

### Extras

The `extra` directory in the same directory as this README resides in contains Chrome/Chromium and Firefox themes, a fix for the Ubuntu-Software-Center when using the dark theme, a Plank theme and an alternative metacity theme, which hides the window titles of maximized windows (doesn't work on Gnome 3.16 and up).

To install the Chrome/Chromium theme go to the `extra/Chrome` folder and drag and drop the Vertex.crx or Vertex-light.crx file into the Chrome/Chromium window. The source of the Chrome themes is located in the source "Chrome/source" folder.

To install the Firefox theme copy the `extra/Firefox/Vertex/chrome` folder to `~/.mozilla/firefox/yourprofile.default/` and restart Firefox.
Make sure that the `tools>options>content>colors use system colors` or `preferences>content>colors use system colors` checkbox is unchecked.
Themes for the variants Vertex-Light and Vertex-Dark are in the Firefox folder, too. Installation is the same.

To install the alternative metacity theme, copy the `Vertex_alt_metacity` folder to `/usr/share/themes` and select it as window theme.

As of version `20200130` the plank theme will be installed along with the normal vertex gtk theme. You can disable the install by passing `disable-plank` to the autogen command. Now open the Plank preferences window by executing `plank --preferences` from a terminal and select `Gtk+` as the theme.

### Troubleshooting

If you get artifacts like black or invisible backgrounds under Unity, disable overlay scrollbars with

    gsettings set com.canonical.desktop.interface scrollbar-mode normal
====

Ubuntu-Software-Center doesn't play nice with dark themes. If you are using Vertex-Dark under Ubuntu the software center will have unreadable text.
To fix this, install the Ubuntu-Software-Center fix. Instructions and relevant files are included in the `extra/Ubuntu-Software-Center` folder.


### Bugs
If you find a bug, please report it at https://github.com/horst3180/Vertex-theme/issues

![alt tag](http://orig09.deviantart.net/c221/f/2015/066/0/4/vertex___theme_by_horst3180-d7s7ycx.jpg)
