# Hotline Miami Collection

> ID #0: Launcher

No language used

> ID #1: Hotline Miami + ID #2: Hotline Miami 2: Wrong Number

1. Get `main` from `exefs`
2. Load it to `Ghidra` using `Ghidra Switch Loader`
3. Disassemble whole `.text` and `.plt` regions
4. After finishing disassembling find `_ZN2nn2oe18GetDesiredLanguageEv` function and go to its only xref
5. In 13th instruction of function change `tbz` to `tbnz`
6. In 14th instruction of function change last value in instruction to `language value`
7. Write changes to ips file

Languages supported via eShop (decimal language value):
- French
- German
- Spanish
- Russian
- Brasilian Portuguese
- English
- Japanese

Languages supported originally (decimal language value):
- Polish (5)
