# Lost Orbit Terminal Velocity

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Load main to `Ghidra` using `Ghidra Switch Loader`
3. Use il2cppdumper, choose first `main` from exefs, then `global-metadata.dat`. It will create `script.json`
4. Open loaded `main`, don't analyze it. Use `ghidra.py` to load script.json
5. After finishing loading and parsing `script.json` run Auto-analyze
6. After finishing auto-analyze find `LanguageManager$$GetSystemLanguage`
7. Find pointer of pointer of StringLiteral that matches your `language acronym`
8. We will be replacing first 4 instructions of `LanguageManager$$GetSystemLanguage` function with:
- `ADRP x8,[pointer offset & 0xFFFFFFF000]` (counting `0x7100000000` as beginning)
- `LDR x8[x8, #[pointer offset & 0xFFF]`
- `LDR x0,[x8]`
- `RET`
9. Create IPS patch with changed values

Languages supported via eshop:
- German
- English
- Spanish
- French
- Italian
- Portuguese
- Russian
- Dutch

Languages supported originally and not possible to choose in game ("`language acronym`"):
- Polish ("`pl`") // confirmed working
