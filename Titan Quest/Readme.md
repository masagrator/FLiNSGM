# Titan Quest

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Run auto-analyze 
4. After finishing auto-analyze go to `_ZN2nn2oe18GetDesiredLanguageEv`
5. Go to first xref
6. Based on decompiled code we can retrieve languages values

```
English - 1
French - 2
Italian - 3
German - 4
Spanish - 5
Russian - 7
Japanese - 8
Chinese - 9
Portuguese - 11 (which is not working)
Dutch - 14
Korean - 15
```
For rest of languages we can find values by searching for function by going to xref of `English` string
7. Change first instruction in function to `mov x0,#[unk]`, where `[unk]` is the language values
8. Second instruction must be `ret`
9. Save changes to IPS and put file to exefs patches

Languages supported via eshop:
- Japanese
- French
- German
- Italian
- Spanish
- Korean
- Russian
- Chinese
- English

Languages mentioned in code (language decimal value):
- Czech (16) // confirmed not working
- Polish (6) // confirmed working
