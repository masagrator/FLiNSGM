# American Fugitive

1. Get `resources.assets` from `romfs\Data\`
2. Open it with UnityEx
3. Find second biggest file in there (`resources_00001.-13`), unpack it, go to `Unity_Assets_Files\resources` and open with HxD
4. Go to the end of file, there will be structure with languages
4. Switch `acronym` and `full string` between language you want to replace and language you want to use (look out to not break size check that is implemented as uint32 before each string)
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
- Simplified Chinese
- Brasilian Portuguese

Languages supported originally and not listed on eShop ("`full string`" / "`acronym`"):
- Polish ("`Polish`" / "`pl`") // confirmed working
