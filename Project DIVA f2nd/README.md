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
- For more details on the files check below

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

---

# PsArc Architecture  

Below is a list of all files found in `data.psarc` and a short description.  
*(I don’t know what all the Textures are—I’ll update this file as needed.)*  

---

## Hatsune Miku Items (`mikitm[ID]`)  

### Modules (000-199)  
- **000** - Miku's face  
- **001** - Hatsune Miku Original Module (Blue Hair, Blue Tie, Hiding in your Wi-Fi...)  
- **002** - Hatsune Miku Append Module  
- **003** - Deep Sky Module  
- **004** - Violet Butterfly Module  
- **005** - Memoria Module  
- **006** - Lab Girl Module  
- **007** - Pierretta Module  
- **008** - Innocent Module  
- **009** - Dark Angel Module  
- **010** - Summer Memories Module  
- **011** - Emerald Module  
- **012** - Solitude Module  
- **013** - Divine Goddess Module  
- **014** - F0newearl Style Module  
- **015** - Kitty Cape Module  
- **016** - Agitation Module  
- **017** - Star Vocalist Module  
- **018** - Heartbeat Module  
- **019** - Pansy Module  
- **020** - Racing Miku 2012 Ver. Module  
- **021** - Factory Tyrant Module  
- **022** - Hello, Good Night. Module  
- **023** - Polka Dot Bikini Module  
- **024** - Swimsuit Module  
- **025** - Yukata Style Module  
- **026** - Running Miku Module  
- **027** - Ribbon Girl Module  
- **031** - Kitty Cat Module  
- **032** - Magician Module  
- **033** - Little Red Module  
- **035** - Out and About Module  
- **037** - Hatsune Miku Butterfly Module  
- **039** - Ichi-no-Sakura Blossom Module  
- **040** - Linkage Module  
- **041** - Rin-chan's #1 Fan Module  
- **042** - Honey Whip Module  
- **045** - Snow Miku 2013 Module  
- **046** - Heart Hunter Module  
- **049** - Conflicted Module  
- **051** - White Dress Module  
- **052** - Vintage Dress Module  
- **053** - Colorful Gumdrop Module  
- **054** - School Module  
- **055** - Orbit Module  
- **056** - Gothic Module  
- **057** - Natural Module  
- **058** - ∞ Module (Infinite Module)  
- **059** - Demons and the Dead Module  
- **060** - Noble Module  
- **101** - Hatsune Miku V3 Module  
- **102** - Supreme Module  
- **103** - Meteorite Module  
- **105** - Chat Noir Module  
- **106** - Hana-Kotoba Module  
- **107** - Kasha Module  
- **108** - Regret Module  
- **109** - Marionette Module  
- **110** - Siren Module  
- **111** - Moonlight Butterfly Module  
- **112** - Avant-garde Module  
- **113** - Liar Module  
- **114** - Urban Pop Module  
- **115** - Rosa Bianca Module  
- **116** - Breath With You Module  
- **117** - Rainbow Lines Module  
- **118** - Orange Blossom Module  
- **119** - Magical Mirai Module  
- **122** - Puffy Pastel Module  

---

### Textures (200-399)  
- **202** - Black Rectangle Texture  
- **203** - Miku Eyes Texture  
- **204** - Violet Butterfly Texture (?)  
- **205** - Black Rectangle Texture 2  
- **206** - Black and Blue Rectangle Texture  
- **207** - Little Black Rectangle Texture  
- **208** - Teal Miku Eyes Texture  
- **209** - Black Rectangle Texture 3  
- **210** - Black Square Texture  
- **214** - Black Square Texture 2  
- **216** - Black Rectangle Texture 4  
- **217** - Black Rectangle Texture 5  
- **219** - Black Square Texture 3  
- **220** - Black Square and Black Rectangle Texture  
- **221** - Black Rectangle Texture 6  
- **239** - Black Rectangle Texture 7  
- **240** - Green Miku Eyes Texture  
- **241** - Black Rectangle Texture 8  
- **242** - Two Black Squares Texture  
- **245** - Dark Teal Miku Eyes Texture  
- **249** - Black Rectangle Texture 9  
- **253** - Black Square Texture 4  
- **255** - Black Square Texture 5  
- **257** - Floating Little Cube 3D Model  
- **258** - Black Square Texture 6  
- **259** - Red Makeup Texture  
- **301** - Black Square Texture 7  
- **303** - Black Rectangle Texture 10  
- **304** - Dimensional Module Eye Texture  
- **305** - Cat Noir Module Eye Texture  
- **306** - Black Rectangle Texture 11  
- **307** - Black Rectangle Texture 12  
- **308** - Black Square Texture 8  
- **309** - Black Square Texture 9  
- **310** - Tealish Eye Texture  
- **311** - 4 Colored Squares Texture  
- **312** - Black Square Texture 10  
- **313** - Black Rectangle Texture 13  
- **314** - Dark Teal Miku Eyes Texture 2  
- **315** - 3 Colored Squares Texture  
- **316** - Black Rectangle Texture 14  
- **317** - Blue Square Texture  
- **318** - Black Square Texture 11  
- **322** - 4 Colored Squares Texture 2  

---

### Hand Models (400-599)  
- **401** - Teal Colored Nails Hand Model  
- **402** - Hatsune Miku Appended Hand Model  
- **403** - Uncolored Nails Hand Model  
- **404** - Violet Butterfly Hand Model  
- **405** - White Gloves Hand Model  
- **406** - Pink Colored Nails Hand Model  
- **407** - Red Colored Nails Hand Model (Breath With You Module?)  
- **408** - Teal Colored Nails Hand Model 2  
- **409** - Green Colored Nails Hand Model  
- **410** - Uncolored Nails Hand Model 2  
- **413** - Green Colored Nails Hand Model 2  
- **414** - Black Fingerless Glove, Teal Nails Hand Model  
- **415** - Kitty Cape Gloves Hand Model  
- **416** - Agitation Gloves Hand Model  
- **417** - Star Vocalist Pink Colored Nails Fingers Model  
- **418** - Teal Colored Nails Fingers Model  
- **419** - Teal Colored Nails Hand Model 3  
- **420** - Light Blue Colored Nails Fingers Model  
- **421** - Factory Tyrant (?) Hand Model  
- **423** - Teal Colored Nails Hand Model 4  
- **426** - White(?) Colored Nail Hand Model  
- **427** - Teal Colored Nails, Shadow on Wrist Hand Model  
- **431** - Kitty Cat Paw Model  
- **432** - Magician(?) Hand Model  
- **433** - Teal Colored Nails Hand Model 5  
- **439** - Kasha(?) Hand Model  
- **440** - Teal Colored Nails Hand Model 6  
- **441** - Orange Colored Nails Hand Model  
- **442** - Crimson Colored Nails Hand Model  
- **445** - White Colored Nails Hand Model  
- **446** - Heart Hunter Hand Model  
- **449** - Uncolored Nails Hand Model 3  
- **451** - Teal Colored Nails Incomplete Left Hand Model  
- **458** - ∞ Hand Model (Infinite Hand Model)  
- **460** - Teal Colored Nails Hand Model 7  
- **503** - Minuscule Spec of Black Dust  
- **504** - Black Gloves Hand Model  
- **505** - Chat Noir Hand Model  
- **506** - Uncolored Nails Hand Model 4  
- **507** - Black Gloves Hand Model 2  
- **508** - Light Teal Colored Nails Hand Model  
- **509** - Marionette Gloves Hand Model  
- **510** - Siren Gloves Hand Model  
- **511** - Moonlight Butterfly Hand Model  
- **513** - Uncolored Nails Hand Model 5  
- **515** - Rosa Bianca Gloves Hand Model  
- **516** - Black Colored Nail Hand Model  
- **517** - Rainbow Lines Hand Model  
- **518** - Orange Blossom(?) Gloves Hand Model  
- **519** - White Gloves Hand Model  
- **522** - Teal Colored Nails Hand Model 8  

---

### Hair Models (600-799)  
- **601** - Hatsune Miku Original Hair Model  
- **602** - Hatsune Miku Append(?) Hair Model  
- **603** - Solitude Hair Model  
- **604** - Violet Butterfly Hair Model  
- **605** - Memoria Hair Model  
- **606** - Blue Hair Texture  
- **607** - Pierretta Hair Model  
- **608** - Innocent Hair Model  
- **609** - Dark Angel Hair Model  
- **610** - Summer Memories Hair Model  
- **611** - Emerald Hair Model  
- **612** - Solitude Hair Model  
- **613** - Divine Goddess Model  
- **614** - F0newearl Style Hair Model  
- **615** - Out and About Hair Model  
- **616** - Agitation Hair Model  
- **617** - Star Vocalist Hair Model  
- **618** - Factory Tyrant Hair Model  
- **619** - Pansy Hair Model  
- **620** - Racing Miku 2012 Ver. Hair Model  
- **621** - Kitty Cape Hair Model  
- **622** - Hello, Good Night. Hair Model
- **623** - Polka Dot Bikini  
- **624** - Swimsuit Hair Model  
- **625** - Yukata Style Hair Model  
- **627** - Ribbon Girl Hair Model  
- **631** - Kitty Cat Hair Model  
- **632** - Magician Hair Model  
- **633** - Little Red Hair Model  
- **635** - ?  
- **637** - Hatsune Miku Butterfly Hair Model  
- **639** - Ichi-no-Sakura Blossom Hair Model  
- **640** - Linkage Hair Model  
- **641** - Rin-chan's #1 Fan Hair Model  
- **642** - Honey Whip Hair Model  
- **645** - Snow Miku 2013 Hair Model  
- **646** - Heart Hunter Hair Model  
- **649** - Conflicted Hair Model  
- **650** - Snow Miku 2013 Alt. Hair Model  
- **651** - White Dress Hair Model  
- **653** - Colorful Gumdrop Hair Model  
- **655** - Orbit Hair Model  
- **656** - Gothic Hair Model  
- **658** - ∞ Hair Model (Infinite Hair Model)  
- **659** - Demons and the Dead Hair Model  
- **660** - Noble Hair Model  
- **701** - Hatsune Miku V3 Hair Model  
- **702** - Supreme Hair Model  
- **703** - Meteorite Hair Model  
- **704** - Dimensional Hair Model  
- **705** - Chat Noir Hair Model  
- **706** - Hana-Kotoba Hair Model  
- **707** - Kasha Hair Model  
- **708** - Regret Hair Model  
- **709** - Marionette Hair Model  
- **710** - Siren Hair Model  
- **711** - Moonlight Butterfly Hair Model  

---

### Notes  
- `(?)` indicates uncertain descriptions.  
- Duplicate IDs (e.g., **413**, **621**) may need verification. 