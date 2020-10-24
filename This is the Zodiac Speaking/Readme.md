# This is the Zodiac Speaking

1. Unpack `main` from `exefs` and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing auto-analyze search for function `UnityEngine.Application$$get_systemLanguage`
7. Change first instruction to `mov x0, #[unk]` where `[unk]` is value attached to language used in Unity.
8. Second instruction should be `ret`
9. Create IPS patch with changed values
10. Put it to Switch

Languages supported via eshop:
- English

Languages supported originally (Unity language value in decimal):
- English (10) // confirmed working
- German (15)
- French (14)
- Russian (30)
- Chinese Simplified (40)
- Polish (27) // confirmed working
- Spanish Latin American (34)