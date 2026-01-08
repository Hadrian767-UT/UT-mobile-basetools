# Downloads

In first, you need to have an computer.

If you don't have, this tutorial is not for u (yet), sorry.

If u have, congratulations!

You can proceed!

In first, download [UndertaleModTool](https://github.com/UnderminersTeam/UndertaleModTool/releases)

This is only avaliable for PC (or no)

Because, GenOuka is making an [UndertaleModTool for Android devices](https://github.com/QiumingOrg/QiuUTMTv4/releases)! (yippee)

Now, still is a little hard use it to porting. Let's wait to the new updates!

But now, backing to the tutorial:

Open UndertaleModTool

You will have an screen like this:

<img width="1920" height="1037" alt="utmt lol" src="https://github.com/user-attachments/assets/8db432dc-fa42-4894-9cf7-6b51dc90fa6c" />

## Encrypted executables

WARNING: If you only have an .exe (even the game being GameMaker), you game maybe is protected!

Maybe your game is encrypted with Enigma VirtualBox/SFX/Enigma Protector!

To discover this, download and install [7-Zip](https://www.7-zip.org/)!

After install it, click with right mouse button in your .exe;

Put the mouse in **7-Zip → Open Inside**

Now, if your .exe is like this: 

<img width="100" height="253" alt="Captura de Tela (68)" src="https://github.com/user-attachments/assets/c558ce88-6c59-490f-a905-f677c089f05a" />

Is Enigma VirtualBox!

Now, if 7-zip give this error:  

<img width="414" height="153" alt="Captura de Tela (69)" src="https://github.com/user-attachments/assets/752e9041-16d4-44aa-9a2b-b6ff93c90ee5" />

Is SFX!

Now, if the .exe is like this:  

<img width="162" height="268" alt="Captura de Tela (70)" src="https://github.com/user-attachments/assets/36067b65-7348-47cc-8d51-072ac6ac7dc4" />

With all the files being the .exe name, Enigma Protector!

## Enigma VirtualBox

Download [EnigmaVBUnpacker](https://mega.nz/file/slJknLSR#ZUOr_vDukmfVuUS-CThF5sIxrQxaY_N3dZeVEd662qQ)!

You will have an screen like this: 

<img width="445" height="386" alt="Captura de Tela (67)" src="https://github.com/user-attachments/assets/56694c6a-435f-48d5-a309-c2ecdb88ac21" />

Now, click in the **three dots**

Select your .exe

And click in **Unpack**!

## SFX

Open your .exe (clicking **Yes** to admin permission), and open File Explorer.

In File Explorer, go to **C:\Users\your-user\AppData\Local\Temp**

Now, filter to **Modification date**

Now, go to newest folder (or the second, idk if you opened something after it)

Now, open it.

See that this folder have all the things that u need? (data.win, original .exe, etc)?

Copy this folder to your Downloads

And now, u can close the game.

## Enigma Protector

But now, if your case is Enigma Protector, i feel so much in say this, but i don't know how to decrypt this, sorry

This even has how decrypt, but is very hard 😭

Now, backing again for porting methods!

# Now, the real porting

Now that u have the data.win, with the UndertaleModTool opened, click in **File → Open** (in the top left corner) or click **Ctrl + O**!

Select your data.win location

And wait the data.win being loaded.

If u have some error in load, open an [issue](https://github.com/UnderminersTeam/UndertaleModTool/issues) and follow the steps showed in hour of create an issue.

Well, with all done, lets tro the steps.

## Step One: Optimization (not mandatory)

### Shaders

In first, you will remove the shaders, like here:

![2026-01-07 21-45-36](https://github.com/user-attachments/assets/4d80830c-c3d6-46cf-a667-60cce53a5a00)

And make it with ALL shaders avaliable in the game, and making the same thing with all codes showed in "Find all references" screen.

### Fonts, Sounds and  Sprites

#### Exportation

##### Fonts

Click in **Scripts → Resource Exporters → ExportAllFonts.csx**

Select the folder that you will put the fonts (i recommend that u create an folder with name "fonts" in the working_directory (directory that the game are located))

And wait the magic happens.

##### Sounds (skip this part if all of your sounds is .ogg)

###### Exportation

Click in **Scripts → Resource Exporters → ExportAllSounds.csx**

Select the folder that you will put the sounds (i recommend that u create an folder with name "sounds" in the working_directory)

And wait the magic happens again.

###### Conversion

Download the [Batch WAV to OGG Converter](https://www.ascensiongamedev.com/files/file/15-batch-wav-to-ogg-converter/)

After downloaded, extract it and run the .exe

Click in **Browse**

Select the folder that u put the sounds

And click in **Convert**

And wait the magic happens for the third time. (oh shit, i can't take any more magics 😭)

##### Sprites

The sprites don't be need to be exported. I will explain it later.

###### Importation

##### Fonts

Click in **Scripts → Resource Importers → ImportAllFonts.csx**

Select the folder that u put the fonts

And wait the fonts being imported.

##### Sounds

Click in **Scripts → Resource Importers → ImportAllSounds.csx**

Select the folder that u put the sounds

And wait the sounds being imported.

##### Sprites

Click in **Scripts → Resource Importers → NewTextureRepacker.csx**

Click in **No** for the question

And wait the sprites being imported.

#### Why i have to do this?

In most of the fangames, the texture size (8192x8192) make the fonts and sprites being ugly, so we make it for correct it.

##### And the sounds?

About the sounds, some games have an exorbitant size of data.win because of the sounds .wav, so we make the conversion to .ogg for correct it.

