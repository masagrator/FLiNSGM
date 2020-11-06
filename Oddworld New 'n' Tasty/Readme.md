# Oddworld New 'n' Tasty

1. Unpack `main` from `exefs`, and `global-metadata.dat` from `romfs/Managed/Metadata`
2. Use `il2cppdumper`, first choose `main` from `exefs`, then `global-metadata.dat`. It will create `dump.cs`
3. Open `global-metadata.dat` with HxD
4. Open `dump.cs`
5. Find in `dump.cs` enum `Language`
6. In `Language` enum you have described how each language string is stored in `global-metadata.dat`
7. Find in `global-metadata.dat` string that is at least the same size as string you want to replace it with
8. Rewrite string with your language string and any additional character that wasn't replaced replace with null (0x00)
9. Save `global-metadata.dat` and put it to `atmosphere/contents/01005E700ABB8000/romfs/Managed/Metadata`

Languages supported via eshop:
- Japanese
- English
- French
- German
- Italian
- Spanish
- Portuguese (Brazilian Portuguese in fact)

Languages supported originally ("Language enum string" / Unity language decimal value)
- Polish ("Polish" / 27)
- Russian ("Russian" / 30)
