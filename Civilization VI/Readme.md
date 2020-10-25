# Civilization VI

1. Unpack `main` from `exefs` and `Vanilla_en_US_iOS.xml` from `romfs/Base/Assets/Text`
2. Load `main` to `Ghidra` using `Ghidra Switch Loader`
3. Run auto-analyze.
4. While auto-analyze is working translate `Vanilla_en_US_iOS.xml` to your language (this is the only file that doesn't exist or is not translated fully for unsupported languages - but is used by Nintendo Switch)
5. When auto-analyze is finished find string `ja-` (use Search -> Memory, it's not converted to string by analyzer because it's too short) and check its references. We are searching for function that looks like this:
```

void * FUN_7100ec246c(void *param_1,int param_2)

{
  size_t __n;
  uint uVar1;
  ulonglong uVar2;
  char *__s;
  undefined8 uStack56;
  undefined8 uStack40;
  
  if (param_1 == (void *)0x0) {
    return (void *)0x0;
  }
  if (param_2 == 0) {
    return param_1;
  }
  uStack40 = GetDesiredLanguage();
  uStack56 = Make(0);
  uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
  if ((uVar2 & 1) == 0) {
    uStack56 = Make(2);
    uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
    if ((uVar2 & 1) == 0) {
      uStack56 = Make(3);
      uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
      if ((uVar2 & 1) == 0) {
        uStack56 = Make(4);
        uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
        if ((uVar2 & 1) == 0) {
          uStack56 = Make(5);
          uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
          if ((uVar2 & 1) == 0) {
            uStack56 = Make(6);
            uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
            if ((uVar2 & 1) == 0) {
              uStack56 = Make(7);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "ko-";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(8);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "nl-";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(9);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "pt-";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(10);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "ru-";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(0xb);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              __s = "zh-Hant";
              if ((uVar2 & 1) != 0) goto LAB_7100ec2708;
              uStack56 = Make(0xc);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "en-GB";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(0xd);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "fr-CA";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(0xe);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) != 0) {
                __s = "es-419";
                goto LAB_7100ec2708;
              }
              uStack56 = Make(0xf);
              uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
              if ((uVar2 & 1) == 0) {
                uStack56 = Make(0x10);
                uVar2 = operator==((LanguageCode *)&uStack40,(LanguageCode *)&uStack56);
                __s = "zh-Hant";
                if ((uVar2 & 1) == 0) {
                  __s = "en-US";
                }
                goto LAB_7100ec2708;
              }
            }
            __s = "zh-Hans";
          }
          else {
            __s = "es-";
          }
        }
        else {
          __s = "it-";
        }
      }
      else {
        __s = "de-";
      }
    }
    else {
      __s = "fr-";
    }
  }
  else {
    __s = "ja-";
  }
LAB_7100ec2708:
  __n = strlen(__s);
  if ((int)(param_2 - 1U) <= (int)__n) {
    __n = param_2 - 1U;
  }
  memcpy(param_1,__s,__n);
  *(undefined *)((longlong)param_1 + (longlong)(int)__n) = 0;
  uVar1 = printf("GetPreferredLanguage : %s\n",param_1);
  return (void *)(ulonglong)uVar1;
}


```
6. Find instructions related to loading offset of strings `en-GB` and `en-US` in this function (ADRP/ADD)
7. Change both of them to read offset of the same language string you want it to use
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
