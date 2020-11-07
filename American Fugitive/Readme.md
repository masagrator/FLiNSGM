# This is the Zodiac Speaking

1. Get `resources.assets` from `romfs\Data\`
2. Open it with UnityEx
3. Find second biggest file in there (`resources_00001.-13`), unpack it, go to `Unity_Assets_Files\resources` and open with HxD
4. Go to the end of file, there will be structure with languages
4. Switch acronym and full language strings between language you want to replace and language you want to use (look out to not break size check that is implemented as u32 before each string)
5. Go back to UnityEx and press "Import files"
6. Put resources.assets to LayeredFS

Languages supported via eshop:
- Japanese
- English
- French
- German
- Spanish
- Korean
- Russian
- Chinese (in fact Simplified)
- Portuguese (In fact Brasilian Portuguese)

Languages supported originally and not listed on eShop ("Full string" / "Acronym"):
- Polish ("Polish" / "pl") // confirmed working
