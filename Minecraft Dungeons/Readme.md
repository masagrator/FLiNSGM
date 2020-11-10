# Minecraft Dungeons

1. Get `pakchunk0-Switch.pak` from `romfs\Dungeons\Content\Paks`
2. Unpack `pakchunk0-Switch.pak` following UnrealPak tutorial
3. Go to `Dungeons\Content\Localization`, in each folder you have localization files categorized by language
4. Copy `*.locres` file from your language folder and replace file in `en` and `en-GB` folder for every category
4. Pack 
```
Dungeons/Content/Localization/Game/en-GB/Game.locres
Dungeons/Content/Localization/Game/en/Game.locres
Dungeons/Content/Localization/InputKeysLoc/en-GB/InputKeysLoc.locres
Dungeons/Content/Localization/InputKeysLoc/en/InputKeysLoc.locres
```
to pak file using UnrealPak tutorial Patch tab

5. Put correctly named pak file to layeredfs

Languages supported via eShop:
- Japanese
- English
- French
- German
- Italian
- Spanish
- Korean
- Portuguese
- Russian
- Chinese Simplified (only in separate release)
- Chinese Traditional (only in separate release)

Languages included in Localization folder ("folder name"):
- Polish ("pl-PL") // confirmed working
- Latin Spanish ("es-MX")
- Brasilian Portuguese ("pt-BR")
- Swedish ("sv-SE")

