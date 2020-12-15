# Horse Farm

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` either:

5.1 Search for `CPlatformInterface$$GetSystemLanguage` and disassemble it manually

or

5.2. Run Auto-analyze and after finishing auto-analyze find `CPlatformInterface$$GetSystemLanguage`

6. Go to the end of function and find `mov w0,w20`. Change it to `mov w0,#[unk]` where `[unk]` is value attached to language used in Unity.
7. Create IPS patch with changed values

Languages supported via eshop:
- German
- English
- Spanish
- French
- Italian
- Dutch
- Portuguese
- Russian

Languages supported originally and not possible to choose in game (Unity language value in decimal):
- Polish (27) // confirmed working
- Czech (7)
- Hungarian (18)
- Romanian (29)