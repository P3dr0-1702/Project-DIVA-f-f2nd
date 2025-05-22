# Project-DIVA-f-f2nd

My GitHub project about modding *Project DIVA f 2nd* for the PS Vita.

As of writing this, none of this has been tested with PS3 data — it all refers to the PS Vita version only.

---

## Requisites  
- CFW PS Vita (HENkaku)  
- `nonpdrm` plugin  
- `RePatch` plugin (**do not use `fd_fix`**)  
- Digital copy of *Hatsune Miku: Project DIVA f 2nd*  
  - If using the physical version, dump the cartridge using MaiDumpTool or a similar tool.

---

## Model Swapping  
*(As of writing this, I only know how to change existing modules)*

### 1 – Download Tools folder  
Inside, you'll find both MikuMikuModel (MMM) and PsArc Extractor. Extract MMM.

### 2 – Decrypt Files  
On the PS Vita's VitaShell, go to `ux0:app/(GAMEID)` (replace `GAMEID` with your game’s ID — in my case it's `PCSE00434` for the US version, which I’ll use from now on).  
Select the folder with **Triangle**, then choose the option **"Open Decrypted"** in the submenu.  
Now navigate inside the `rom/` folder and copy the `data.psarc` file to another location. For now, placing it in the root of `ux0:` is fine. This file contains most of the game's data.

### 3 – Get files from VitaShell  
Take out your SD card (FTP or USB works too) and plug it into your PC using an adapter.  
Make sure your PC is set to show **hidden files**, and copy the `data.psarc` file from the SD card to your computer.

### 4 – Extract files  
Open PsArc Extractor and click on **"Unpack PSARC/MSELF"**.  
Select your `data.psarc` and let it run — it might take a while due to the file size, but **do not interrupt** the process or the repacking might fail later.

### 5 – MMM Configuration  
Open MMM and choose **Configuration**.  
Either go to your newly extracted folder and locate `BONE_DATA.BON`, or download it from this Git.  
For *f 2nd*, you only need to set up the bone database.  
So just select "Bone Database" and load the `BONE_DATA` file (it can be `.BON` or `.bin`).

### 6 – Open the desired file  
You can browse the extracted files to find models.  
They usually follow this naming pattern: the first 3 letters of the character's name + `"itm"` + a number.  
For example:  
- Miku’s default model = `mikitm001`  
- `mikitm000` refers to Miku's face  

For this guide, we'll use `mikitm001`. Open it in MMM.

### 7 – Dump the model  
After selecting a model in MMM, you'll see 4 files on the right.  
Right-click the `.osd` file and choose **Export** → select a folder → export as **FBX Exporter**.

### 8 – Blender  
Open Blender → File > Import > FBX (.fbx) → select your exported FBX file.  
Before importing, in the right-hand panel:  
- Under "Armature", set:  
  - Primary Bone Axis: **X Axis**  
  - Secondary Bone Axis: **Y Axis**  
Then import the model.

### 9 – Make your changes  
**Do not delete or modify bones**, or the model may break in-game.  
You're free to edit the mesh — just be careful.  
(I'm no Blender expert, so I won’t be giving Blender-specific tutorials.)

### 10 – Export  
Go to File > Export > FBX (.fbx)  
In the right panel:  
- Under **"Apply Scalings"**, choose **"FBX Unit Scale"**  
- Under **"Armature"**:  
  - Primary Bone Axis: **X Axis**  
  - Secondary Bone Axis: **Y Axis**  
Then export.

### 11 – Back to MMM  
Open the original model again in MMM.  
Go to the right panel, but this time choose **Replace** instead of Export.  
Select the modified FBX file you exported from Blender.  
Accept the confirmation windows.  
Make sure the model appears T-Posing, upright, and the feet are touching the grid.  
If not, something went wrong.  
If everything looks good, save and exit MMM.

### 12 – Repack  
Open PsArc Extractor and click **"Pack PSARC/MSELF"**.  
Choose the folder containing the modified `mikitm001`, and let it finish.  
Once done, rename the output file to `data.psarc`.

### 13 – Back into the Vita  
Place the new `data.psarc` into:  
`ux0:RePatch/PCSE00434/rom/`  
Create the folders if they don’t exist.

### 14 – Run your game and enjoy!  
The `RePatch` plugin will load your modified file, allowing you to play the game with the new models!