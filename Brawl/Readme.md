# BRAWL

Known issues: Font doesn't support all characters needed to run all included languages. Changing texts may result in rendering glitched text.

1. Get `resources.assets` from `romfs\Data`
2. Open `resources.assets` in `UnityEX`
3. Extract `Localization.txt`
4. Rename `Localization.txt` to `Localization.csv`
5. Open `Localization.csv` in `OpenOffice calc`
6. Move column with your language so it will be 2nd column
6. Save file, rename `Localization.csv` to `Localization.txt`
7. Import file in `UnityEX`
8. Put `resources.assets` to layeredfs

Languages supported via eShop:
- English

Languages supported via `Localization.txt` ("Language string")
- Polish ("POLISH") // confirmed working
- Russian ("RUSSIAN")
- Finnish ("FINNISH")
- Spanish ("SPANISH")
- French ("FRENCH")
- Italian ("ITALIAN")
- Dutch ("DUTCH")
- Norwegian ("NORWEGIAN")
- Brasilian Portuguese ("PORTUGUESE_BR")
- Swedish ("SWEDISH")
- German ("GERMAN")
- Japanese ("JAPANESE")