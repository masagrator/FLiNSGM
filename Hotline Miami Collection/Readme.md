# Hotline Miami Collection

> ID #0: Launcher

No language used

> ID #1: Hotline Miami + ID #2: Hotline Miami 2: Wrong Number

1. Get `main` from `exefs`
2. Load it to `Ghidra` using `Ghidra Switch Loader`
3. Disassemble whole `.text` and `.plt` regions
4. After finishing disassembling find `_ZN2nn2oe18GetDesiredLanguageEv` function

NOTE: Values are stored in different weird ways. Because only Polish language is not available in game on Switch, I have found out that Polish is stored as negative value, so next instructions were done in a way that will work only with languages stored as negative values

5. In 13th instruction of function change `tbz` to `tbnz`
6. In 14th instruction of function change last value in instruction to `language value`
7. Write changes to ips file

Languages supported via eShop (decimal language value):
- French
- German
- Spanish
- Russian
- Portuguese (Brasilian)
- English

Languages supported originally (decimal language value):
- Polish (7)