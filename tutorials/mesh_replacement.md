# Mesh Replacement

**NOTE** - check the [textures tutorial](texture_modding.md) where I explain how to unpack in much more detail.

To replace a mesh in EWTP, we'll need to first export the mesh file using [UE Viewer](https://www.gildor.org/en/projects/umodel#files)
Exported mesh format is `.psk` and animations are in `.psa` format.

In order to be able to modify these models, we'll need to use Blender and install an [extension for importing and exporting Unreal PSK and PSA files.](https://github.com/DarklightGames/io_scene_psk_psa)

Once you're done modifying the mesh, drop the 3D model in Unreal Engine 4.9, cook contents for windows and take UE created `.uasset` and patch it for modding. ([patching tutorial here](uasset_editing.md))

