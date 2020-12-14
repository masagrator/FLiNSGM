# Dark Souls Remastered

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Auto-Analyze it
4. After finishing Auto-Analyze find `_ZN2nn2oe18GetDesiredLanguageEv` function
5. Go to first xref
6. In first instruction of this function put `mov w0,#[unk]` where `[unk]` is `language value`
7. In second instruction put `ret`
8. Create IPS patch and put it to your exefs patches

Languages supported via eShop (Decimal `language value`):
- English (0 / 6 / 10 / 11 / 12 /)
- French (1)
- German (2)
- Italian (3)
- Spanish (4)
- Dutch (5)
- Portuguese (7)
- Brasilian Portuguese (8)
- Russian (9)

Languages supported originally (Decimal `language value`):
- Polish (13) // Partially working (font doesn't support Polish characters)
- Czech
- Danish
- Finnish
- Greek
- Hungarian
- Norwegian
- Swedish
- Turkish