# Human: Fall Flat

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` either:

5.1 Search for `SwitchDLL$$GetDesiredLanguage` and disassemble it manually

or

5.2. Run Auto-analyze and after finishing auto-analyze find `SwitchDLL$$GetDesiredLanguage`

6. Go to the function it's branching immediately
7. Change first instruction to `mov x0, #[unk]` where `[unk]` is `language value`.
8. Second instruction should be `ret`
9. Create IPS patch with changed values
10. Put it to Switch

Languages supported via eshop (`language value` in decimal):
- English (11)
- French (15)
- German (17)
- Japanese (24)
- Italian (23)
- Korean (25)
- Russian (33)
- Simplified Chinese (44)
- Spanish (37)

Languages supported originally and not possible to choose in game (`language value` in decimal):
- Portuguese (30) // Confirmed working
- Brasilian Portuguese
- Thai
- Turkish
- Ukrainian
- Traditional Chinese
- Polish (29) // Confirmed working
