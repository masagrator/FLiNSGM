# Civilization VI

1. Unpack `main` from `exefs` and `Vanilla_en_US_iOS.xml` from `romfs/Base/Assets/Text`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Run auto-analyze.
4. While auto-analyze is working translate `Vanilla_en_US_iOS.xml` to your language (this is the only file that doesn't exist or is not translated fully for unsupported languages - but is used by Nintendo Switch)
5. When auto-analyze is finished find string `pl-` and check its references. We are searching for function that looks like this:
```

```
6. Find instructions related to loading offset of strings `en-GB` and `en-US` in this function (ADRP/ADD)
7. Change them to read offset of the same language string you want it to use
8. Write IPS file and put it to exefs_patches
9. change name of `Vanilla_en_US_iOS.xml` to match your language and copy it to `atmosphere/contents/010044500C182000/romfs/Base/Assets/Text`

Languages listed by eshop:
- Japanese
- French
- German
- Italian
- Spanish
- Korean
- Portuguese
- Russian
- Chinese
- English

Languages supported originally and not possible to choose in game (language string / romfs file name):
- Polish (`pl-` / `Vanilla_pl_PL_iOS.xml`) // confirmed working with audio