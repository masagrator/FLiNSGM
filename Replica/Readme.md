# Replica

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing auto-analyze find `_ZN2nn8settingseqERKNS0_12LanguageCodeERKNS0_8LanguageE` and go to one of xrefs (all are redirecting to the same function)
7. At the end of decompiled function you will find address to struct. Go there
8. Find 2 uint32_t values `0xA` and change it to `Unity language value`
9. Find function `I2.Loc.LocalizationManager$$set_CurrentLanguage` and return it instantly
10. Create IPS patch with changed values
11. Put it to Switch

Languages supported via eshop:
- German
- English
- Spanish
- French
- Italian
- Japanese
- Korean
- Brasilian Portuguese
- Russian
- Chinese Simplified

Languages supported originally and not possible to choose in game (Unity language value in decimal):
- Polish (27) // confirmed working
