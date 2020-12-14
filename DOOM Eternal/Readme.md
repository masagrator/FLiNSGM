# DOOM Eternal

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` with `Ghidra Switch Loader`
3. Auto-Analyze main
4. After finishing Auto-Analyze find position of your `language string` in memory and save its offset 
5. Find function `_ZN2nn2oe18GetDesiredLanguageEv_0` and go to xref
6. Check for instructions ADRP/ADD that are giving offset for `english` string and replace it with offset for your `language string`
7. Save changes to IPS patch

> How to force different audio (audio of your language is set by default)
1. Based on `english` string we need to find two functions. They are looking almost the same (calls most of `language string` existing), only difference is that one function returns `language audio string`, second returns `language audio value`.
2. Change in one function your `language audio string` offset called here somewhere to different `language string` offset
3. In second function change returned your `language audio value` to different `language audio value`.
4. Save changes to IPS patch

Put IPS patch to exefs patches

Languages supported via eShop ("language string" / "language audio string" / "language audio value"):
- English ("english" / "English(US)" / "0")
- German ("german" / "German" / "2")
- French ("french" / "French(France)" / "1")
- Italian ("italian" / "Italian" / "3")
- Japanese ("japanese" / "Japanese" / "4")
- Brasilian Portuguese ("portuguese" / "Portuguese(Brazil)" / "8")
- Russian ("russian" / "Russian" / "6")
- Spanish ("spanish" / "Spanish(Spain)" / "7")
- Latin Spanish ("latin_spanish" / "Spanish(Mexico)" / "9")
- Traditional Chinese ("traditional_chinese" / no audio / no audio)
- Simplified Chinese ("simplified_chinese" / no audio / no audio)
- Korean ("korean" / no audio / no audio)

Other supported languages ("language string" / "language audio string" / "language audio value")
- Polish ("polish" / "Polish" / "5")
