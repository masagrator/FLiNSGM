# Fractured Minds

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Auto-Analyze it
4. After finishing Auto-Analyze find `LocalizationManager$$init` function
6. Find in this function first occurence of `mov w1,wzr` and change it to `mov w1,#[unk]` where `[unk]` is `language value`
7. Create IPS patch and put it to your exefs patches

Languages supported via eShop:
- English
- French
- German
- Italian
- Japanese 
- Korean 
- Brasilian Portuguese
- Russian
- Simplified Chinese
- Spanish

Languages supported originally (Decimal `language value`):
- Polish (6) // confirmed working