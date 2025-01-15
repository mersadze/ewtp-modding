# .Uasset Modding

Modifying `.uasset` files without some third-party software can be a little difficult.
Usually, if you've got the right Unreal Engine version installed (the one which matches the engine game was made in), you can oftentimes open any **.uasset** file (It could be a texture, mesh, animation, material, blueprint, etc.)

**Note:** I wasn't able to open only BP (**Blueprint**) `.uasset` files even whilst using the correct engine.

The tool I've been using is [UAssetGUI](https://github.com/atenfyr/UAssetGUI)
It can be used for `.uasset` file low-level examination - as stated in repo

# Patching

To patch the modified `.uasset`, simply recreate the folder structure of the file's origin, put the modified file inside and use [UnrealPak](https://github.com/RiotOreO/unrealpak) to create a patch `.pak` file. Give your patch a name and add `_P` in the end so that engine recognizes it as a priority and overrides original `.uasset` file, replacing it with your modified one.

