# Saints Row The Third

Recommended is to use IDA since Ghidra has issues with proper disassembling this main (IDA also, but not as bad as Ghidra and it's enough for this case). 

> Full methodology:
1. Load `main` from exefs to IDA using nxo64.py with `Enabled` in Analyze window unchecked
2. Force convert whole `.text` and `.plt` to `code` without deleting already assigned info
3. After finishing conversion enable analyze
4. After finishing analyze find function `nn::settings::LanguageCode::Make(nn::settings::Language)` and go to xref (it should be only one)
5. We should be now in code not converted to function. Find where this chunk of code starts, highlight code from the beginning (excluding first NOP) to the moment it will be before next function. Now go to Edit -> Functions -> Create function. Wait a moment until analyzer will finish the job.
6. By some code examining I have found that engine has defined all supported languages and one string that contains used languages in game - in our case `US DE ES FR IT NL CZ PL RU`. 
By searching instructions reading strings like "SE" or "ES" we can find that they are in some order. I have assumed that if US is 0 (because it doesn't exist in this list), then if it starts from ES it must be 1 for comparison that you can find in vicinity of `nn::settings::LanguageCode::Make(nn::settings::Language)`. So:
> US - 0
>
> ES - 1
>
> IT - 2
>
> JP - 3
>
> DE - 4
>
> FR - 5
>
> NL - 6
>
> SE - 7
>
> DK - 8
>
> CZ - 9
>
> PL - 10
>
> SK - 11
>
> RU - 12
>
> CH - 13
8. Because I can't find comparison for US, I have used ES as donator. Slightly above `nn::settings::LanguageCode::Make` call in this function it should be instruction `mov W8, #1`. Change `1` to the language value
9. Write IPS file and put it to exefs patches
10. Create new file `config.ini`, paste to it:
```ini
[override_config]
override_language=es
```
Save it.
11. Copy `config.ini` to `atmosphere/contents/0100DE600BEEE000`

---

> Shorted methodology
1. Load `main` from exefs to IDA using nxo64.py with `Enabled` in Analyze window unchecked
2. Force convert whole `.text` and `.plt` to `code` without deleting already assigned info
3. After finishing conversion enable analyze
4. After finishing analyze find function `nn::settings::LanguageCode::Make(nn::settings::Language)` and go to xref (it should be only one)
5. Above xref it should be instruction `mov W8, #1`. Change `1` to the language value
6. Write IPS file and put it to exefs patches
7. Create new file `config.ini`, paste to it:
```ini
[override_config]
override_language=es
```
Save it.
Explanation: I couldn't figure out how to replace English detection. Any other language can be used, I have decided to use Spanish as donator.

8. Copy `config.ini` to `atmosphere/contents/0100DE600BEEE000`

---

Languages listed by eshop:
- English
- French
- German
- Italian
- Spanish 
- Dutch
- Russian
- Japanese (in separate release with previous languages - titleid: 0100FBC00C6BA000)

Languages originally included and not possible to choose in game (language value):
- Polish (10) // confirmed working
- Czech (9)
