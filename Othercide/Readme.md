# Othercide

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` either:

5.1 Search for `UnityEngine.Application$$get_systemLanguage` and disassemble it manually

or

5.2. Run Auto-analyze and after finishing auto-analyze find `UnityEngine.Application$$get_systemLanguage`

6. Change first instruction to `mov x0, #[unk]` where `[unk]` is value attached to language used in Unity.
7. Second instruction should be `ret`
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

Languages supported originally and not possible to choose in game (Unity language value in decimal):
- Polish (27) // confirmed working
