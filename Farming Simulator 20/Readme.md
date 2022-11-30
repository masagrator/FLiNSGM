# A Boy and his Blob

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Auto-Analyze it
4. After finishing Auto-Analyze find `_ZN2nn2oe18GetDesiredLanguageEv` function
5. Go to first xref
6. Find in this function near the end `mov w20,wzr` and change it to `mov w20,#[unk]` where `[unk]` is `language value`
7. Create IPS patch and put it to your exefs patches

Languages supported via eShop (Decimal `language value`):
- English (0 / 2)
- Dutch
- French (5)
- German (1)
- Italian
- Portuguese
- Brasilian Portuguese
- Russian
- Simplified Chinese
- Spanish
- Traditional Chinese

Languages supported originally (Decimal `language value`):
- Polish (3) // confirmed working
- Czech
- Turkish
- Hungarian
- Guarani(?)
- Romanian
