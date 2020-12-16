# LIMBO

NOTE: It is adviced to not use solely Ghidra. Use either IDA or IDA + Ghidra (Ghidra can't find xrefs for `_ZN2nn2oe18GetDesiredLanguageEv`)

1. Load `main` from exefs to IDA using nxo64.py with `Enabled` in Analyze window unchecked
2. Force convert whole `.text` and `.plt` to `code` without deleting already assigned info
3. After finishing conversion enable analyze
4. After finishing analyze find function `nn::oe::GetDesiredLanguage(void)` and go to xref (it should be only one)
5. In lower part of function we need to find `mov r6,#0x0` and change it to `mov r6,#[unk]` where `[unk]` is your `language value`
6. Save changes to IPS file

Languages listed by eshop:
- Japanese
- English
- French
- German
- Italian
- Spanish 
- Korean
- Russian
- Portguese
- Brasilian Portguese
- Chinese Simplified
- Chinese Traditional

Languages supported originally ("decimal `language value`")
- Polish ("`11`") // confirmed working
- Turkish ("`13`")
