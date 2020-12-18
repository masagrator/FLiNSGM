# Outlast 2

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Run Auto-analyze
4. After finishing auto-analyze go to `_ZN2nn2oe18GetDesiredLanguageEv`
5. Go to its xref (which is `_Z17appGetLanguageExtv`)
6. Find in this function 2x ADRP/ADD instruction calling pointer to unicode32 string `INT`
7. Change them to call pointer to unicode32 string of your language
8. Save changes to IPS patch and copy patch to exefs patches

Languages supported via eShop:
- Japanese
- English
- French
- German
- Italian
- Spanish
- Portuguese (Brasilian in fact)
- Russian

Languages available in `main` ("unicode32 string")
- Polish ("POL") // confirmed working
