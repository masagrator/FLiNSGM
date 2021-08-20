# Sniper Elite 4


1. Get `main` from `exefs`
2. Load `main` to `Ghidra` with `Ghidra Switch Loader`
3. Auto-Analyze main
4. After finishing Auto-Analyze find position of your `language string` in memory and save its offset 
5. Find function `_ZN2nn2oe18GetDesiredLanguageEv_0` and go to xref which returns `language value` (different than `LanguageCode*`)
6. Immediately return `language value`

Officially supported languages (`language value`):
- English (`6')
- French (`1`)
- CanadianFrench (`1`)
- Italian (`3`)
- German (`2`)
- Spanish (`4`)
- LatinAmericanSpanish (`4`)
- Russian (`5`)
- Japanese (`7`)
- SimplifiedChinese (`15`)
- TraditionalChinese (`16`)
- Korean (`17`)
- Portuguese (`9`)
- Anything else (`0`)

Confirmed existing languages in code (`language value`):
- Polish (`14`) #Missing files. Copy them from PC version for exefs patch to work. Just replacing english files won't work.
