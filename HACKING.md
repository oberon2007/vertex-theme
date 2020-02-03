This theme uses libsass/gulp to process the sass/*.scss. Never edit any of the .css files manually.

#### Editing the CSS based themes in the `common` directory

* Edit the cinnamon.css file.

* Edit the sass/*.scss files (gnome-shell or gtk-3.0).

* Run `make` to generate all css files using sassc (gnome-shell or gtk-3.0).

--

#### Editing the images in the `assets` folder

* Open the `assets.svg` file in inkscape. Each object in the .svg file corresponds to an image in the `assets` folder.

* Find the object you want to edit and make your changes. Important: Don't change the obejct id.

* Save `assets.svg` and delete the images corresponding to the edited .svg objects from the `assets` folder (or just delete everything in the `assets` folder).

* Run `./render-assets.sh` from a terminal.
