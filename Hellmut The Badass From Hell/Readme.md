# Hellmut: The Badass From Hell

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use `il2cppdumper`, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing auto-analyze find function `nn.oe.Language$$GetDesired`
7. Go to xref named `SwitchManager$$_GetLanguage`
8. Based on `dump.cs` generated with `il2cppdumper` we know that this function returns `SystemLanguage` enum (the same as used by `UnityEngine.Application$$get_systemLanguage` in some other games)
9. Change first instruction to `mov x0, #[unk]` where `[unk]` is value attached to language used in Unity.
10. Second instruction should be `ret`
8. Create IPS patch with changed values
9. Put it to Switch

Languages supported via eshop:
- English
- French
- German
- Italian
- Spanish
- Russian

Languages supported originally and not possible to choose in game (Unity language value in decimal):
- Polish (27) // confirmed working
- Czech (7)
- Brasilian Portuguese (There is not Brasilian Portuguese as SystemLanguage, only Portuguese as 28)
- Japanese (22)
- Korean (23)
- Chinese Traditional (There is no differentation between Simplified and Traditional in SystemLanguage, only `Chinese` as 6)
- Chinese Simplified (There is no differentation between Simplified and Traditional in SystemLanguage, only `Chinese` as 6)