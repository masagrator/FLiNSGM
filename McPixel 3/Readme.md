# McPixel 3

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` with `Ghidra Switch Loader`
3. Auto-Analyze main
4. After finishing Auto-Analyze find position of your `language string` in memory and save its offset 
5. Find function `_ZN2nn2oe18GetDesiredLanguageEv_0` and go to xref
6. Check for instructions ADRP/ADD that are giving offset for `en` string and replace it with offset for your `language string`
7. Save changes to IPS patch

Put IPS patch to exefs patches

Languages supported via eShop ("language string"):
- English ("en")
- German ("de")
- French ("fr")
- Japanese ("jp")
- Brasilian Portuguese ("po")
- Russian ("ru")
- Spanish ("es")
- Traditional Chinese ("tc")
- Simplified Chinese ("sc")
- Korean ("kr")

Other supported languages ("language string" / "language audio string" / "language audio value")
- Polish ("pl") // Confirmed working, game is saving language in "settings.json", so for patch to work you cannot have this file in save
