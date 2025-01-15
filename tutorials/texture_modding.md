# Texture Modding

Modding textures for EWTP (or any **UE4 game**) involves unpacking game files, altering files and then patching the modified files.
**Below are the links to the tools** you'll need for texture modding.

- [UnrealPak](https://github.com/RiotOreO/unrealpak)
- [UE Viewer](https://www.gildor.org/en/projects/umodel#files)
- [UE4-DDS-Tools](https://github.com/matyalatte/UE4-DDS-Tools)

## Getting Started: Tools

Before starting the modding process, extract the tool zip files.

## Unpacking

- Create a new folder on your desktop, call it whatever you want (e.g. EWTP-Extracted), it'll be the folder **where you'll be extracting the game files**
- Go to game's root folder
- Navigate to `\EmilyWantsToPlay\Content\Paks`

In this directory, you'll see a large `.pak` file called `EmilyWantsToPlay-WindowsNoEditor`, this is the **file that contains entire game contents**, every `Blueprint`, `Texture`, `Mesh`, etc.

In order to extract the content from this `.pak`, simply drag and drop the file onto the `UnrealPak` - `UnrealUnpak.bat` batch file.
This will start an execution process which will create a new directory containing the game files.

## Textures

After the program has finished the unpacking process, head to the folder `EmilyWantsToPlay-WindowsNoEditor` - this directory will have the game files along with *engine's configurations*.

If you check any folder inside this dir, you'll see that files are in `.uasset` format, in order to unpack these files, we need to use [UE Viewer](https://www.gildor.org/en/projects/umodel)

- Download and extract the archive
- Open the `umodel.exe`

Once you've opened the **.exe** , in the path input, select the `EmilyWantsToPlay` dir from the extracted game folder (`EmilyWantsToPlay-WindowsNoEditor\EmilyWantsToPlay`).
Now check the checkbox `Override game detection` and choose **Unreal Engine 4** and in the second dropdown, select the engine version `4.9`.

If you also want to export the `Sound`, `ScaleForm (UE3)`, `FaceFX (UE3)` files, check those too.

Below that you can choose the `UE3 package compression` (*for now, we'll just leave it as default*)
Same goes with **Platform** `auto`.

Now click open, you'll see a file browser open up. Here you can choose and see the *meshes*, *materials*, *textures*, etc.
*There's a [full guide](https://www.gildor.org/en/projects/umodel) on their website on how to use it.*

Now in order to extract everything at once, right-click the /Content folder and choose export option.
It will open up the window where you'll have to select the path you want your exports to be dropped in and **Texture format** *which is completely up to you.*

Once the extraction is done, head to the exports directory and you'll see that game files had been successfully unpacked.
There are lot's of folders containing textures, choose one particular texture file and create a separate folder in your working environment where you'll copy this file in.

Go ahead and alter or change the texture the way you want to and when you're done, open the `UE4-DDS-Tools` **.exe**, select the **original .uasset** file (*the one you've copied*), then select the altered texture file and lastly choose folder where you'll export it.

## Creating Patch

Once you've created **.uasset** version of your modified texture, go ahead and create a folder structure similar to the texture file's origin, like this: `EmilyWantsToPlay-WindowsNoEditor\EmilyWantsToPlay\Content\Textures\Props\Habitation`.

Drop your modified **.uasset** file inside the last dir of the created structure and use `UnrealPak` batch file (`UnrealPak-With-Compression`) to pack it.

This will create a new `.pak` file, but in order for this patch to work, we'll have to add `_P` at the end of the file name, like this: `EmilyWantsToPlay-WindowsNoEditor_P.pak`, this way the engine will recognize it as higher priority and replace the original texture with the one you've made.

Once you're done with this process, drop the `.pak` file inside games `\EmilyWantsToPlay\Content\Paks` dir and launch the game, you will see your texture now.