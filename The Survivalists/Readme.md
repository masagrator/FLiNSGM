# The Survivalists

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing auto-analyze find `Team17.StringLocalization.Localization$$GetLanguage`
7. In decompiled window find code 
```
                        *(undefined4 *)(*(long *)(Team17.StringLocalization.Localization_TypeInfo + 0xb8) + 0x48) = 0;
```
Find instruction related to this `mov w8,wzr` and change it to `mov w8,#[unk]` where `[unk]` is `languagev value`
8. Create IPS patch with changed values
9. Put it to Switch

Languages supported via eshop:
- German
- English
- Spanish
- French
- Italian
- Japanese
- Korean
- Portuguese
- Russian
- Chinese

Languages supported originally and not possible to choose in game (Language value in decimal):
- Polish (7) // confirmed working
- Arabic (?)
- Dutch (?)