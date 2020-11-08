# DOOM

Note: mentioned `language acronym` may not have any role here, I just didn't have time to test anymore if this gives anything. For sure `language string` is important

1. Get `main` from `exefs`
2. Load `main` to `Ghidra` with `Ghidra Switch Loader`
3. Auto-Analyze main
4. After finishing Auto-Analyze find position of your `language string` in memory and save it's offset 
5. Find function `_ZN2nn2oe18GetDesiredLanguageEv_0` and go to xref (which should be `_Z25Sys_SetLanguageFromSystemv`)
6. Check for instructions ADRP/ADD that are giving offset for `english` string and replace it with offset for your `language string`
7. Go to offset of `pt` string and replace this string with your `language acronym`
8. Go back to `_Z25Sys_SetLanguageFromSystemv` and replace offsets for `en` and `en-GB` with offset to your `language acronym`
9. Save changes to IPS patch

> How to force different audio
1. Based on `english` string I have found function `_ZN21idSoundHardware_WWise17idLangToWWiseLangER5idStr`
2. Change your `language string` offset called here somewhere to different `language string` offset
3. Save changes to IPS patch

Put IPS patch to exefs patches

Languages supported via eShop ("language string"):
- English ("english")
- German ("german")
- Italian ("italian")
- Japanese ("japanese")
- Portuguese ("portuguese")
- Russian ("russian")
- Spanish ("spanish")

Languages supported originally ("language string" / "language acronym")
- Polish ("polish" / "pl")
- Latin Spanish ("latin_spanish" / `n/d`)
