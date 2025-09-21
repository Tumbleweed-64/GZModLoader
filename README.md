# GZModLoader
A lightweight mod launcher for GZDoom written in Java. You can also call it "GZML" for short, which is pronounced like "dismal," but with a G instead of a D at the start.

## Features

- Load GZDoom mods. Duh.
- Run multiple mods (not actually a feature yet, but working on it)
- Run all special instructions for mods by containing them in `.gzml` files, which is a file file format I created for the purpose of this project.


# .gzml File Format

The `.gzml` file is basically a standard text file with weird formatting that I invented. Basically it functions as a simple way to register and run your GZDoom mods from the app. To use them, put a `.gzml` file in the directory of each of your mods. This application assumes that you have a mod folder setup like:

```
doom_mods
|
|___mod1
|___mod2
|___mod3
|___etc...
```

As I was saying, create a `.gzml` file in each mod folder, and set them up like the example below.

### Example .gzml File

```
modName=Brutal Doom v21 Gold
run=brutal.pk3
```

That's it! I may add more configuration options later, but for now, all you need is the mod's name, and how to run it. The application takes the data on the "run" line, and runs it with the `gzdoom` command, so in this line you may include flags like `-iwad` or `deh` for mods with more complicated setup. If you do not include a `.gzml` file in the mod's directory, the application will assume that there is no complicated setup, and will run the first `.pk3` or `.wad` file it finds within the directory.
