# Downloads

In first, you need to have an computer.<br />
If you don't have, this tutorial is not for u (yet), sorry.<br />
If u have, congratulations!<br />
You can proceed!<br />
In first, download [UndertaleModTool](https://github.com/UnderminersTeam/UndertaleModTool/releases)<br />
This is only avaliable for PC (or no)<br />
Because, GenOuka is making an [UndertaleModTool for Android devices](https://github.com/QiumingOrg/QiuUTMTv4/releases)! (yippie)<br />
Now, still is a little hard use it to porting. Let's wait to the new updates!<br />
But now, backing to the tutorial:<br />
Open UndertaleModTool<br />
You will have an screen like this:<br />
<img width="1920" height="1037" alt="utmt lol" src="https://github.com/user-attachments/assets/8db432dc-fa42-4894-9cf7-6b51dc90fa6c" />

## Encrypted executables

WARNING: If you only have an .exe (even the game being GameMaker), you game maybe is protected!<br />
Maybe your game is encrypted with Enigma VirtualBox/SFX/Enigma Protector!<br />
To discover this, download and install [7-Zip](https://www.7-zip.org/)!<br />
After install it, click with right mouse button in your .exe;<br />
Put the mouse in `7-Zip → Open Inside`<br />
Now, if your .exe is like this: <br />
<img width="100" height="253" alt="Captura de Tela (68)" src="https://github.com/user-attachments/assets/c558ce88-6c59-490f-a905-f677c089f05a" /><br />
Is **Enigma VirtualBox**!

Now, if 7-zip give this error:<br />
<img width="414" height="153" alt="Captura de Tela (69)" src="https://github.com/user-attachments/assets/752e9041-16d4-44aa-9a2b-b6ff93c90ee5" /><br />
Is **SFX**!

Now, if the .exe is like this:<br />
<img width="162" height="268" alt="Captura de Tela (70)" src="https://github.com/user-attachments/assets/36067b65-7348-47cc-8d51-072ac6ac7dc4" /><br />
With all the files being the .exe name, is **Enigma Protector**!<br />

## Enigma VirtualBox

Download [EnigmaVBUnpacker](https://mega.nz/file/slJknLSR#ZUOr_vDukmfVuUS-CThF5sIxrQxaY_N3dZeVEd662qQ)!<br />
You will have an screen like this:<br />
<img width="445" height="386" alt="Captura de Tela (67)" src="https://github.com/user-attachments/assets/56694c6a-435f-48d5-a309-c2ecdb88ac21" /><br />
Now, click in the `three dots`<br />
Select your .exe<br />
And click in `Unpack`!<br />
After finished, the folder named `%DEFAULT FOLDER%` is the folder that have the original files from the encrypted .exe!

## SFX

Open your .exe (clicking `Yes` to admin permission), and open File Explorer.<br />
With the game opened, in File Explorer, go to `C:/Users/your-user/AppData/Local/Temp`<br />
Now, filter to `Modification date`<br />
Now, go to newest folder (or the second, idk if you opened something after it)<br />
Now, open it.<br />
See that this folder have all the things that u need? (data.win, original .exe, etc)?<br />
Copy this folder to your Downloads<br />
And now, u can close the game.

## Enigma Protector

But now, if your case is Enigma Protector, i feel so much in say this, but i don't know how to decrypt this, sorry<br />
This even has how decrypt, but is very hard 😭<br />

## Encrypted data.win

If u have an error in **UndertaleModTool**, like this:<br />
<img width="292" height="152" alt="Captura de Tela (75)" src="https://github.com/user-attachments/assets/9aebe73f-a597-4c72-8357-3551719a7d33" /><br />
U have to do this step!<br />
If u not have this error, u can skip this step!<br />

**1.** Open the **data.win** in the [**Notepad++**](https://notepad-plus-plus.org/downloads/)!<br />
**2.** In the first four characters, change the word on these characters to **FORM**!<br />
**3.** Now, click **Ctrl + S** to save your modified **data.win**!<br />

Your **data.win** should open now!  <br />
Now, backing again for porting methods!

# Now, the real porting

Now that u have the data.win, with the UndertaleModTool opened, click in `File → Open` (in the top left corner) or click `Ctrl + O`!<br />
Select your data.win location<br />
And wait the data.win being loaded.<br />

> **WARNING:** If you have an warning like this:<br />
<img width="407" height="159" alt="Captura de Tela (74)" src="https://github.com/user-attachments/assets/178c0f41-2da3-42d5-b979-302b53c83cf6" /><br />
> It means that your game is **YYC** (compiled with native code, it means, **C++**), it means that the game can't be ported, because of the code.  

If u have some error in load, open an [issue](https://github.com/UnderminersTeam/UndertaleModTool/issues) and follow the steps showed in hour of create an issue.<br />
Well, with all done, lets to the steps.

## Step One: Optimization (not mandatory)

### Shaders

In first, you will remove the shaders, like here:<br />
![2026-01-07 21-45-36](https://github.com/user-attachments/assets/4d80830c-c3d6-46cf-a667-60cce53a5a00)<br />
And make it with ALL shaders avaliable in the game, and making the same thing with all codes showed in **Find all references** screen, using the **Find all references** in this functions:<br />

```gml
shader_set;
shader_reset;
shader_set_uniform;
shader_get_uniform;
shader_set_uniform_*
shader_set_uniform_*_array
```
> **WARNING:** The * symbol means any letter<br />
For example:<br />
shader_set_uniform_f;<br />
shader_set_uniform_f_array;<br />
And others.
> 
> **OTHER WARNING:** As i speaked before, you have to do this step in all codes, minus in **GMLive** scripts (codes with **GMLive** name), is not necessary to delete it from **GMLive** too.
>
> **WARNING 3:** If there's an object called **BLUR_SHADER**/**blur_shader**/**gaussian_blur**/**camera_blur**/other name, u have to delete ALL things in the **Draw GUI (64)** code!<br />
> U should to delete **almost all** things in the **Create (0)** code, keeping the code like this:<br />
> ```gml
> draw_set_color(c_white);
> depth = -100000;
> alarm[0] = 30;
> ```

### Fonts, Sounds and  Sprites

### Exportation

##### Fonts

Click in `Scripts → Resource Exporters → ExportAllFonts.csx`<br />
Select the folder that you will put the fonts (i recommend that u create an folder with name "fonts" in the working_directory (directory that the game are located))<br />
And wait the magic happens.

##### Sounds (skip this part if all of your sounds is .ogg)

##### Exportation

Click in `Scripts → Resource Exporters → ExportAllSounds.csx`<br />
Select the folder that you will put the sounds (i recommend that u create an folder with name "sounds" in the working_directory)<br />
And wait the magic happens again.<br />
> **WARNING:** If you have any .ogg file in working_directory, cut these files to the sounds folder!

###### Conversion

Download the [Batch WAV to OGG Converter](https://www.ascensiongamedev.com/files/file/15-batch-wav-to-ogg-converter/)

After downloaded, extract it and run the .exe<br />
Click in `Browse`<br />
Select the folder that u put the sounds<br />
And click in `Convert`<br />
And wait the magic happens for the third time. (oh shit, i can't take any more magics 😭)

##### Sprites

The sprites don't be need to be exported. I will explain it later.

### Importation

##### Fonts

Click in `Scripts → Resource Importers → ImportFonts.csx`<br />
Select the folder that u put the fonts<br />
And wait the fonts being imported.

##### Sounds

Click in `Scripts → Resource Importers → ImportSounds.csx`<br />
Select the folder that u put the sounds<br />
Click `Yes` for all, minus the last (audiogroup name)<br />
And wait the sounds being imported.

##### Sprites

Click in `Scripts → Resource Importers → NewTextureRepacker.csx`<br />
Click in `No` for the question<br />
And wait the sprites being imported.

#### Why i have to do this?

In most of the fangames, the texture size (8192x8192) make the fonts and sprites being ugly (only in 4GB RAM or minus, making too the game just crash in 2GB RAM in some cases), so we make it for correct it.

#### And the sounds?

About the sounds, some games have an exorbitant size of data.win because of the sounds .wav, so we make the conversion to .ogg for correct it.

## Step Two: Mobile Corrections

### Locale Fix

#### Editing scripts

In first, do what this gif is making: <br />
![2026-01-07 22-50-59](https://github.com/user-attachments/assets/9f2d1c82-5d38-4559-8c8b-d1aea7aec667)
(pls don't care about the Batch WAV to OGG Converter screen in keyboard image, it was an thing that i forgot to disable 😭)<br />
It need to have done because if u don't do it, the `locale/` folder don't will work and u will got an error, and will no have sprites and fonts iin dialogs (if the game use)

#### Editing the .txt files inside the folder

Use your favorite notepad (i recommend to u use [Notepad++](https://notepad-plus-plus.org/downloads/)!)<br />
Open these files in the notepad: <br />
<img width="107" height="157" alt="Captura de Tela (71)" src="https://github.com/user-attachments/assets/6c343699-7ce3-4bfe-914f-c51c6efa5409" /><br />
(if there's other language name in `locale/` what have these files, do it to these folder too)<br />
With the files opened, you will remove the `./` from the start of the paths, like this:  

![2026-01-08-08-46-47](https://github.com/user-attachments/assets/e90887df-220f-4c2e-bd8d-57bbd38e37b6)

### Console_Init Error Fix

In first, again, see what are the game's GMS! (is in the top of the UTMT)
If your GMS if 2023 or more, skip this step!
But if your GMS is 2022.9 or minus, continue!
After this, do what this gif is making:<br />
![2026-01-07 23-05-56](https://github.com/user-attachments/assets/49598b0b-eebf-489c-92d3-9c425a7622cc)<br />
Do the same thing in this codes:<br />

> Console_Uninit<br />
> Console_Output<br />
> Console_OutputLine<br />
> Console_Clear<br />
> Console_GetInputNumber<br />
> Console_GetInput<br />
> Console_PopInput<br />
> Console_SetVisible<br />
> Console_IsVisible<br />
> Console_SetStatusText<br />
> Console_SetStatusNumber<br />
> Console_SetStatusRatio<br />
> Console_Init

## Step Three: Mobile Stuff (Controls)

Download the [Mobile Controls Code](https://github.com/Hadrian767-UT/UT-mobile-basetools/blob/main/Undertale%20Hadrian's%20Mobile%20Controls.zip)<br />
Extract it

### MobileKey

#### Sprites

Click in `Scripts → Resource Importers → ImportGraphics.csx`<br />
Select the `mobile-controls-location/MobileKey/MK Codes/Sprites (crosu)`<br />
(pls, don't use the sprite in `Sprites` location, is my sprite and i didn't authorize nobody to use it.)<br />
Click in `Yes`<br />
Click in `Ok` when it finish.<br />
After it, search **spr_mobilekey** in search tab<br />
Click in triangle in tab `Sprites` in `Data` (tab in the left of the screen)<br />
Select the **spr_mobilekey** sprite<br />
And modify the **Origin** (x = 32, y = 32)

#### Sounds

Click in `Scripts → Resource Importers → ImportAllSounds.csx`<br />
Select the `mobile-controls-location/Sounds`<br />
Click `Yes` for all, minus the two last (First: IsDecompressedOnLoad; Second: audiogroup name)<br />
Click in `Ok`<br />
And wait the sounds be imported.

#### Fonts

Click in `Scripts → Resource Importers → ImportFonts.csx`<br />
Select the `mobile-controls-location/MobileKey/Fonts (TianQi Buttons)`<br />
(TianQi is the chinese that create the buttons style from my MK, credit him if you will upload your port)<br />
And wait the fonts being imported.

#### Codes

Click in `Scripts → Resource Importers → ImportGML.csx`<br />
Select the `mobile-controls-location/MobileKey/MK Codes/Codes (TianQi Buttons)`<br />
Click in `Yes`<br />
And wait the codes being imported.

#### Objects

Click in the arrow, in the left side of **Objects** name<br />
Roll the scroll bar until the end<br />
And click two times in the **obj_mk** object.<br />
Activate the **Persistent** flag, clicking in the box with the name **Persistent** in right side<br />
And change **Group** to **1**.

### Joystick

#### Sprites

Click in `Scripts → Resource Importers → ImportGraphics.csx`<br />
Select the `mobile-controls-location/Joystick/Sprites`<br />
Click in `Yes`<br />
Click in `Ok` when it finish.

#### Fonts

Click in `Scripts → Resource Importers → ImportFonts.csx`<br />
Select the `mobile-controls-location/Joystick/Fonts`<br />
And wait the fonts being imported.

#### Script

Click in `Scripts → Run other script`<br />
Select the `mobile-controls-location/Joystick/idkmobilecontrols4/TouchControlsEnabler0830.csx`<br />
(the `TouchControlsEnabler0403.csx` version is for the UTMT 0.4.0.3)<br />
Click in `Yes` (if an dialog appear, annd the dialog only appear if the data.win name isn't "UNDERTALE")

#### Objects

Click in the arrow, in the left side of **Objects** name<br />
Roll the scroll bar until the end<br />
And click two times in the **obj_mobilecontrols** object.<br />
And change **Group** to **1**.

### Arrows 

#### Script

Click in `Scripts → Run other script`<br />
Select the `mobile-controls-location/ArrowsYippie/TouchControlsEnabler0830.csx`<br />
Click in `Yes` (if an dialog appear, annd the dialog only appear if the data.win name isn't "UNDERTALE")

#### Objects

Click in the arrow, in the left side of **Objects** name<br />
Roll the scroll bar until the end<br />
And click two times in the **obj_mobilecontrols** object.<br />
And change **Group** to **1**.

### Dual Clicker

Click in `Scripts → Resource Importers → ImportGML.csx`<br />
Select the `mobile-controls-location/Dual Clicker NEW/obj_cc`<br />
Click in `Yes`<br />
> **COOL THINGS:** If you want to activate DEBUG button, just modify the variable `global.debug_legally` (it is in the code `gml_Object_obj_cc_Create_0`, change this value of `0` to `1`

# Now, we will make the controllers appear

Search `world` in search bar, and click in the code<br />

```
gml_Object_world_Other_2
```
And above the line<br />

```gml
instance_create_depth(0, 0, 0, closed_captions);
```

Add:

```gml
instance_create_depth(0, 0, -15998, obj_cc);
```

# Now, we will make the closed_captions always visible! (or almost visible) 

Searching `closed_captions`, in the code:

```
gml_Object_closed_captions_Create_0;
```

in the line (for 2.3 or more)<br 

```gml
enum UnknownEnum
{
    Value_m100 = -100
}
```

or in the line (for 2.2.2.302 or minus)

```gml
depth = 100;
```

We will switch Value_m100 (2.3 or +) or the depth (2.2.2.302 or -) for

```gml
2.3+:

enum UnknownEnum
{
    Value_m100 = -15800
}

2.2.2.302-:

depth = -15800;
```

Now, in the code:

```
gml_Object_closed_captions_Step_0;
```

In the line: 

```gml
2.3+:

enum UnknownEnum
{
    Value_m200 = -200,
    Value_1 = 1,
    Value_3 = 3
}

2.2.2.302-:

inst.text = "{instant true}{alpha 1}{gui true}{scale 2}{depth " + string(200) + "}" + text + "&";
```

we will switch for:

```gml
2.3+:

enum UnknownEnum
{
    Value_m200 = -15900,
    Value_1 = 1,
    Value_3 = 3
}

2.2.2.302-:

inst.text = "{instant true}{alpha 1}{gui true}{scale 2}{depth " + string(-15900) + "}" + text + "&";
```
# And all done in PC (at least for modifying)!

To save your progress, click in `File → Save` or click **Ctrl + S**
And click in **Enter** two times!

# Moving the files for your phone

After u continue, u have to move files to your phone!<br />
Use the **FileZilla** or an **USB cable connected in computer** to pass the files! (if u want to use the **FileZilla**, you have to use [this app](https://play.google.com/store/apps/details?id=com.alphainventor.filemanager&hl=pt_BR))

## Using FileZilla

After install the app, go to **Access from...** (or other name, is the last square, in the right)<br />
After it, click in **START**.

In **FileZilla**, put the informations that the app shows.<br />
And press **Enter**.<br />
Mark the unchecked option, and click **Enter**.<br />

After it, click on **device/** folder (in right)<br />
Create a new folder (pressing the **right button** of the mouse)<br />
Put any name for folder<br />
In left, go to your game directory<br />
And upload the **data.win**, **locale** folder and some important file for game (if it have) to your phone. (selecting the files, pressing the **right button** of mouse, and clicking **Upload**)<br />

## Using USB

Just connect the USB in your PC and in your phone
Create the folder
And copy your files to here.

# Just more one thing before to the APK things...

Some times, the GMS version what show in UTMT not is totally correct, because it read an specific part of the data.win, what GMS writes a little different of the original...<br />
But, if your GMS is 2022.9 or minus, do you know that you can see what is the REAL GMS runtime version?<br />
Yes, you can!<br />
Just see the `Embedded Images`, the original runtime version will be in the name of the all of these Embedded Images!<br />
So sad that YoYo remove it in 2023+ versions :(<br />
But anyways, if you have problems with found an correct APK, it can help you a bit :)

# Now, we will do the things in phone!

In first, download [MT Manager](https://github.com/Hadrian767-UT/UT-mobile-basetools/blob/main/MT%20Manager.apk)<br />
And after, download the [APKs for porting](https://github.com/Hadrian767-UT/UT-mobile-basetools/tree/main/GMS-APKs) (download the apk that your data.win use, if any APK is missing, write in issues, sending your data.win and the missing GMS APK)<br />
After download and install `MT Manager`, create an folder in any local with any name

## Moving files

Copy the `data.win`, the `locale/` folder and the APK for the GMS of you data.win.<br />
Rename the `data.win` to `game.droid`<br />
And copy your `game.droid` and the `locale/` folder to the `assets/` folder from the APK that u are using.

## Modifying the APK

Now, u will learn `how to modifying an existent APK like it if yours`!

### Step One: Cloning your APK

Make it like this gif is making:<br />
![Screen_Recording_20260108_081513_MT Manager](https://github.com/user-attachments/assets/d6121802-351d-4028-9c00-9d88003bb187)

**IMPORTANT THING THAT I FORGOT TO MENTION:** When you are cloning the APK, make sure that the option `Use old cloning method` is enabled!

If u don't make this, your APK will crash when u run it (there's a way to correct it with the option disabled, but enable it is better)<br />
Now, open the `resource.arsc` file in your APK!<br />
Clicking in `Search resource value`, search the APK actual name.<br />
Now, see that have two strings with the same name?<br />
Edit this two strings with the APKs name that u want to put!

### Step Two: Modifying options

In first, u will open the `assets/options.ini` from your APK!<br />
Then, you will edit it, like this:<br />
![Screen_Recording_20260108_121138_MT Manager](https://github.com/user-attachments/assets/e67c8d8e-8335-4ef6-97ab-b7efe0d87449)

#### What is your-apk-code?

Is basically the numbers marked in the photo below:<br />
![Screenshot_20260108_095011_MT Manager](https://github.com/user-attachments/assets/e55d7428-be84-4873-b8a2-6dda6872f9c7)<br />
First Number: MajorVersion<br />
Second Number: MinorVersion<br />
Third Number: BuildVersion<br />

### Step Three: Creating modified icons (not mandatory)

#### Dumping the original icon

Download and install [Resource Hacker](https://www.angusj.com/resourcehacker/#download)<br />
After it, follow the steps for this gif:<br />
![2026-01-08-14-19-08](https://github.com/user-attachments/assets/2299c712-3b32-4ed3-8574-3c7325d4c74c)

#### Making the new icon for Android

In first, download [adaptive_bg](https://github.com/Hadrian767-UT/UT-mobile-basetools/blob/main/adaptive_bg.png) and [adaptive_icon](https://github.com/Hadrian767-UT/UT-mobile-basetools/blob/main/adaptive_icon.png)<br />
Now, in your browser, enter in [Pixlr](https://pixlr.com)<br />
Open the **AI Photo Editor**<br />
Click in the blue button with the **+**<br />
Select the **adaptive_icon.png**<br />
Click in the local marked in photo:<br />
<img width="1618" height="950" alt="Captura de Tela (72)" src="https://github.com/user-attachments/assets/7cbe6193-de7a-4c57-b0cd-a41794da4560" /><br />
Select **Image**<br />
Select your dumped .ico<br />
And put the .ico in center, like this icon that i made:<br />
<img width="162" height="162" alt="adaptive_icon" src="https://github.com/user-attachments/assets/d2fdcabf-9fb4-4efc-8039-bafc776dd4cc" /><br />
Click in **Save**<br />
After it, click in **Save as**<br />
Save it with the same name (**adaptive_icon.png**)

#### Putting new icon in APK

In first, go to the folder `res/` from the APK<br />
See? There two different types of this folder<br />
In some APKs, the **res/** folder will look like this (more organized):<br />
![Screenshot_20260108_162354_MT Manager](https://github.com/user-attachments/assets/bc6c2c94-9e03-42e9-8539-544c9e0ff02a)<br />
But in the others, will look like this (or the same that here or with different name files but with the same structure) (like the folder has been obfuscated):<br />
![Screenshot_20260108_162404_MT Manager](https://github.com/user-attachments/assets/b5ffd030-4825-444f-9401-5b99867cd426)<br />
But don't worry! For all the two there's an way to put your icons!

##### Normal method

Just copy the files (**adaptive_icon** and **adaptive_bg**) to all the folders that have the name "**-v26**" in the last characters.

##### Obfuscated method

In **MT Manager**, clicking in the APK that u are using, click in the icon<br />
After this, click in **OK**<br />
Now, u have an .zip with all icons from the APK in the same directory that the APK is!<br />
Click in the .zip (named **APK-NAME_icon.zip**)<br />
After it, click in the `res/` folder and delete ALL files (.xml and the .png that have just an icon that fills all the image), leaving here just the .png that are the **adaptive_icon** and **adaptive_bg**<br />
In APK directory, create an folder named "icons" (or other name that u want to use)
Copy the files **adaptive_icon** and **adaptive_bg** to this folder and copy these files more five times
Now, replace the files names to the name files of the .zip, replacing the **adaptive_icon** normal names to the obfuscated names and the same to the **adaptive_bg**.
After it done, put the modified .pngs in `res/` location of the APK.

### Step Four (the last of all): Modify date and time of APK

In **MT Manager**, clicking in the APK and after in **VIEW**, press the `assets/` folder, click in **Property**.
After this, click in **MORE**, and in **Modify time**
In the box, replace the actual time to:

```
1981-01-01 01:01:02
```

And do this in ALL folders and files, leaving the **META-INF** folder for last.

# And done!

Thank you so much for reading!<br />
I write it all in 2 days! It was hard, but i get it!<br />
Good luck in your porting career!<br />
And don't forget for the last important. No make ports all the time, go take care of yourself!<br />
And happy 2026 for u all!<br />

# Just more one warning...

If you want to make an translation of this tutorial for your native language, feel free to do it! I will support and allow it!
Goodbye and cya :3
