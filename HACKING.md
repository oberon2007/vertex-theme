#### Editing the CSS based themes in the `common` directory

* Edit the cinnamon.css file.

* Edit the sass/*.scss files (gnome-shell or gtk-3.0).

* Run `sassc sass/gnome-shell.scss gnome-shell.css` to generate the .css file for gnome-shell.

* Run `sassc sass/gtk.scss gtk.css`, `sassc sass/gtk-dark.scss gtk-dark.css` and `sassc sass/gtk-light.scss gtk-light.css` to generate .css files for gtk-3.0.

Note: `make install` will generate gnome-shell and gtk-3.0 .css files using sassc. The last two steps are not needed.

--

#### Editing the images in the `assets` folder

* Open the `assets.svg` file in inkscape. Each object in the .svg file corresponds to an image in the `assets` folder.

* Find the object you want to edit and make your changes. Important: Don't change the obejct id.

* Save `assets.svg` and delete the images corresponding to the edited .svg objects from the `assets` folder (or just delete everything in the `assets` folder).

* Run `./render-assets.sh` from a terminal.
