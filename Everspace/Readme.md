# Everspace

1. Get `pakchunk0-Switch.pak` from `romfs\RSG\Content\Paks`
2. Unpack `pakchunk0-Switch.pak` following UnrealPak tutorial
3. Go to `RSG\Content\Localization`, in each folder you have localization files categorized by language
4. Copy `*.locres` file from your language folder and replace file in `en` folder for every category
4. Pack 
```
RSG/Content/Localization/Logbooks/en/Logbooks.locres
RSG/Content/Localization/BaseGame_ShortTexts/en/BaseGame_ShortTexts.locres
RSG/Content/Localization/Codex/en/Codex.locres
RSG/Content/Localization/Dialogs/en/Dialogs.locres
```
to pak file using UnrealPak tutorial Patch tab

5. Put correctly named pak file to layeredfs

Languages supported via eShop:
- Japanese
- French
- German
- Italian
- Korean
- Spanish
- Portuguese
- Russian
- English

Languages included in Localization folder ("folder name"):
- Polish ("pl") // confirmed working
- Chinese ("zh-CN")
- Taiwanese ("zh-TW")

