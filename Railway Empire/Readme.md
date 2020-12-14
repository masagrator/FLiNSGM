# Railway Empire

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` with `Ghidra Switch Loader`
3. Auto-Analyze main
4. After auto-analyze find `_ZN2nn2oe18GetDesiredLanguageEv` and go to its xref
5. Find in this function `mov w8,#0x6c70`. Change `0x6c70` to `language value`
6. Save changes to IPS file

Languages supported officialy via eShop:
- English
- French
- German
- Italian
- Spanish
- Russian
- Chinese Simplified
- Korean
- Japanese

Languages existing in original release ("language value"):
- Polish ("0x6c70") // confirmed working