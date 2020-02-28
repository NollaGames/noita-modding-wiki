
# Publishing mods in Steam Workshop (needs Steam version of Noita):

Preparation
---
1) The mod's folder should exist inside Noita\mods\

2) Create a file called workshop.xml inside the mod's folder with the following contents:

	`<Mod`<br>
		`name="YOUR_MOD_NAME_HERE"`<br>
		`description="YOUR_MOD_DESCRIPTION_HERE"`<br>
		`tags="TAGS"`<br>
		`dont_upload_folders="FOLDER_TO_IGNORE1|FOLDER_TO_IGNORE2"`<br>
		`dont_upload_files="FILE_TO_IGNORE1|FILE_TO_IGNORE2"`<br>
	`> `<br>
	`</Mod>`<br>
where 
- YOUR_MOD_NAME_HERE and YOUR_MOD_DESCRIPTION_HERE are replaced with the name and description of your mod. You can use empty description in case you'd rather set the description through the mod's Steam workshop page (the description is not updated if the field is empty).
- TAGS is a comma-separated list of tags applying to the mod.<br>Currently the following tags are available:
	`gameplay`
	`graphics`
	`quality of life`
	`translations`
	`perks`
	`spells`
	`player characters`
	`loadouts`
	`biomes`
	`total conversions`
	`game modes`
	`creatures`
	`bosses`
	`alchemy`
	`tweaks`
	`items`
	`audio`
	`cheats`
	`funny`<br>
Tag names must be spelled exactly as above, in lowercase. Feel free to tell us if you feel a tag is missing.
- FOLDER_IGNORE1 and so on are folders that shouldn't be uploaded separated with | (For example: `dont_upload_folders="ignore_this|files\ignore_this_subfolder"`).
- FILE_IGNORE1 and so on are files that shouldn't be uploaded separated with | (For example: `dont_upload_folders="secret_dev_file.txt"`).

3) Create a file called workshop_preview_image.png inside the mod's folder. This file will be used as the 
mod's preview image in Steam Workshop. The image should have 16:9 aspect ratio.

Other: 
- Mods that have request_no_api_restrictions="1" don't work through Steam Workshop.
- Only the following file types are uploaded:
	`.txt`
	`.csv`
	`.bmp`
	`.xml`
	`.png`
	`.lua`
	`.frag`
	`.vert`
	`.bank`
	`.bin`
- Git folders (.git) are ignored automatically.
- If you remove your mod from Steam Workshop and upload it again later, workshop_id.txt has to be first removed from the mod folder. `"Steam - workshop upload failed: 2"` might be an indicator of this.

Uploading using the upload wizard
---
1) Make sure you're logged into your Steam account.
2) Navigate into your Noita directory using a command line. 
3) Run the following command (or use workshop_upload.bat shipped with the game):<br>
	`noita_dev.exe -workshop_upload`

Batch upload:
---
1) Make sure you're logged into your Steam account.
2) Navigate into your Noita directory using a command line. 
3) Run the following command:<br>
	`noita_dev.exe -workshop_upload MOD_NAME -workshop_upload_change_notes CHANGE_NOTES`<br>
where MOD_NAME is the name of the mod folder inside the mods/ folder, for example nightmare<br>
and where CHANGE_NOTES is the update's change notes or empty.<br>
This allows uploading mods without any interrupts from the UI.

# Publishing without Steam
[ModWorkshop](https://modworkshop.net/game/noita) is a popular repository for hosting Noita mods,