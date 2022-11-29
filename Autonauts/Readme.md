# Autonauts

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` either:

5.1 Search for `SettingsManager$$SetLanguage` and disassemble it manually

or

5.2. Run Auto-analyze and after finishing auto-analyze find `SettingsManager$$SetLanguage`

6. Find in function first instruction that is `mov w20, w1` and change it to `mov w20, #[unk]` where `[unk]` is `language value``
7. Create IPS patch with changed values
8. Put it to Switch

Languages supported via eshop / language value:
- English
- German
- French
- Spanish
- Brasilian Portuguese
- Korean
- Russian
- Simplified Chinese
- Japanese

Languages supported originally and not possible to choose in game / language value:
- Polish / 8 (confirmed working)
- Turkish
