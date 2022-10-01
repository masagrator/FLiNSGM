# Hokko Life

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` either:

5.1 Search for `Hokko.Core.Loc$$get_currentLanguage` and disassemble it manually

or

5.2. Run Auto-analyze and after finishing auto-analyze find `Hokko.Core.Loc$$get_currentLanguage`

6. Change first instruction to `mov x0, #[unk]` where `[unk]` is `language value`
7. Second instruction should be `ret`
8. Create IPS patch with changed values
9. Put it to Switch

Languages supported via eshop / language value:
- English / 0
- German / 3
- French / 1
- Spanish / 4
- Italian / 2
- Brasilian Portuguese
- Korean
- Russian / 5
- Chinese / 6 + 8

Languages supported originally and not possible to choose in game / language value:
- Polish / 9 (Confirmed working)
- Japanese / 7 (Confirmed working)
