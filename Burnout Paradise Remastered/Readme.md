# Burnout Paradise Remastered

1. Get `main` from `exefs`
2. Load it to `Ghidra` using `Ghidra Switch Loader`
3. Run Auto-Analyze
4. After finishing Auto-Analyze find `_ZN2nn2oe18GetDesiredLanguageEv` function
5. Find function that looks like this in decompiled view
```cpp

ulonglong FUN_71000b1e10(void)

{
  int iVar1;
  uint uVar2;
  undefined8 local_18;
  
  local_18 = nn::oe::GetDesiredLanguage();
  iVar1 = memcmp(&local_18,"en-US",6);
  if (iVar1 == 0) {
    return 7;
  }
  iVar1 = memcmp(&local_18,"en-GB",6);
  if (iVar1 == 0) {
    return 8;
  }
  iVar1 = memcmp(&local_18,"ja",3);
  if (iVar1 == 0) {
    return 0x10;
  }
  iVar1 = memcmp(&local_18,"de",3);
  if (iVar1 == 0) {
    return 0xb;
  }
  iVar1 = memcmp(&local_18,"fr",3);
  if (iVar1 == 0) {
    return 10;
  }
  iVar1 = memcmp(&local_18,"fr-CA",6);
  if (iVar1 == 0) {
    return 10;
  }
  iVar1 = memcmp(&local_18,"es",3);
  if (iVar1 == 0) {
    return 0x16;
  }
  iVar1 = memcmp(&local_18,"es-419",7);
  if (iVar1 != 0) {
    iVar1 = memcmp(&local_18,"it",3);
    uVar2 = 0xf;
    if (iVar1 != 0) {
      uVar2 = 7;
    }
    return (ulong)uVar2;
  }
  return 0x16;
}
```

Based on that we now know some languages values

```
English(US) - 7
English(GB) - 8
Japanese - 16
German - 11
French - 10
Spanish - 22
Italian - 15
```

For other languages we need to guess value 

6. Change 0x7 from `orr w0,wzr,#0x7` at `71000b1f14` and `mov w0,#0x8` at `71000b1f24` to other value so `return 7` and `return 8` in decompiled view will change to our value.
7. Write IPS patch and put it to exefs_patches

Languages supported via eShop:
- English
- Japanese
- German
- French
- Spanish
- Italian

Languages supported originally (decimal language value):
- Polish (19) // confirmed working