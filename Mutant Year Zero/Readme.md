# Mutant Year Zero

1. Get `ZoneUE4-Switch.pak` from `romfs\ZoneUE4\Content\Paks`
2. Unpack `ZoneUE4-Switch.pak` following UnrealPak tutorial
3. Go to `ZoneUE4\Content\Localization`, in each folder (except `ConsoleText`) you have localization files categorized by language
4. Copy `*.locres` file from your language folder and replace file in `en` and `en-GB` folder for every category
4. Pack 
```
ZoneUE4/Content/Localization/Cutscenes/en/Cutscenes.locres
ZoneUE4/Content/Localization/Cutscenes/en-GB/Cutscenes.locres
ZoneUE4/Content/Localization/MYZGUI/en/MYZGUI.locres
ZoneUE4/Content/Localization/MYZGUI/en-GB/MYZGUI.locres
ZoneUE4/Content/Localization/MYZSubs/en/MYZSubs.locres
ZoneUE4/Content/Localization/MYZSubs/en-GB/MYZSubs.locres
```
to pak file using UnrealPak tutorial Patch tab

5. Put correctly named pak file to layeredfs

Languages supported via eShop:
- Japanese
- French
- German
- Italian
- Spanish
- Korean
- Russian
- Chinese
- Portuguese (In fact Brasilian)
- English

Languages included in Localization folder ("folder name #1" / "folder name #2"):
- Polish ("pl" / "pl-PL") // confirmed working

