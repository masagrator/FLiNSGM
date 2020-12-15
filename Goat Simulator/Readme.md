# Goat Simulator

NOTE: It is adviced to not use solely Ghidra. Use either IDA or IDA + Ghidra (Ghidra can't find xrefs for `_ZN2nn2oe18GetDesiredLanguageEv`)

1. Load `main` from exefs to IDA using nxo64.py with `Enabled` in Analyze window unchecked
2. Force convert whole `.text` and `.plt` to `code` without deleting already assigned info
3. After finishing conversion enable analyze
4. After finishing analyze find function `nn::oe::GetDesiredLanguage(void)` and go to xref (it should be only one)
5. We need to find two instructions in this function:
  - `movw       r4,#0x4906`
  - `movt       r4,#0x544e`
  
  First instruction contains 2 last bytes of `language value`. Second instruction 2 first bytes of `language value`

6. Change both instructions so in summary they will give us `language value`
7. Save changes to IPS file

Languages listed by eshop:
- Japanese
- English
- French
- German
- Italian
- Spanish 
- Korean
- Dutch
- Russian
- Portguese
- Chinese

Languages supported originally ("`language string`" / "`language value`")
- Polish ("`POL`" / "`0x4c4f5006`")
- Turkish (n\d / n\d)
