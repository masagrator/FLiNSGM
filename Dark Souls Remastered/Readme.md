# Dark Souls Remastered

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Auto-Analyze it
4. After finishing Auto-Analyze find `_ZN2nn2oe18GetDesiredLanguageEv` function
5. Go to first xref
6. In decompiling window we need to find lines using `nn::settings::LanguageCode::Make(0)` and `nn::settings::LanguageCode::Make(0xC)`. After comparing both of them you can see that it's assigning value `0` to variable. 0 = English
7. Change in instructions `wzr` in `mov w19, wzr` to number assigned to your language.
8. Create IPS patch and put it to your exefs patches

Languages supported via eShop:
- English
- Japanese (only via separate release)
- French
- German
- Italian
- Spanish
- Korean
- Portuguese
- Russian
- Chinese

Languages supported originally (Decimal value):
- Polish (5) // Confirmed working
