# Mages of Mystralia

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing Auto-Analyze go to `GameLanguage$$GetLanguageFromCode`
7. Change first three instructions `mov w2,#0x1` to `mov w2,#[unk]` where `[unk]` is value attached to language used in game.
8. Create IPS patch with changed values
9. Put it to Switch

Languages supported via eshop:
- Japanese
- French
- German
- Italian
- Spanish
- Korean
- Russian
- Chinese Simplified
- English

Languages supported originally and not possible to choose in game (Game language value in decimal):
- Polish (9) // confirmed working
- Hungarian (11)