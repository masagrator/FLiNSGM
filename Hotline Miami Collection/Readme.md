# Hotline Miami Collection

> ID #0: Launcher

No language used

> ID #1: Hotline Miami + ID #2: Hotline Miami 2: Wrong Number

1. Get `main` from `exefs`
2. Load it to `Ghidra` using `Ghidra Switch Loader`
3. Disassemble whole `.text` and `.plt` regions
4. After finishing disassembling find `_ZN2nn2oe18GetDesiredLanguageEv` function and go to its only xref
5. Change first instructions to `[lang]` of your language of choice
7. Change next instruction to `ret`
8. Write changes to ips file

Languages supported via eShop (`lang`):
- French (`mov x0, #1; LSL #32, mov x0, #2`)
- German (`mov x0, #-0xfffc; movk x0, #0x0, LSL #16`)
- Spanish (`mov x0, #-0xfffb; movk x0, #0x0, LSL #16`)
- Russian (`mov x0, #-0xfff8; movk x0, #0x0, LSL #16`)
- Brasilian Portuguese (`mov x0, #1; LSL #32, mov x0, #6`)
- English (supports anything that is not matching other languages)
- Japanese (`mov x0, #-0xfff7; movk x0, #0x0, LSL #16`)

Languages supported originally (decimal language value):
- Polish (`mov x0, #-0xfff9; movk x0, #0x0, LSL #16`)
