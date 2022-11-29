# A Boy and his Blob

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Auto-Analyze it
4. After finishing Auto-Analyze find `_ZN2nn2oe18GetDesiredLanguageEv` function
5. Go to first xref
6. In first instruction of this function put `mov w0,#[unk]` where `[unk]` is `language value`
7. In second instruction put `ret`
8. Create IPS patch and put it to your exefs patches

Languages supported via eShop (Decimal `language value`):
- English (0)

Languages supported originally (Decimal `language value`):
- Polish
- Japanese (6) // confirmed working
- French (1) // confirmed working
- German (2) // confirmed working
- Spanish (3) // confirmed working
- Brasilian Portuguese (4) // confirmed working
- Russian (5) // confirmed working