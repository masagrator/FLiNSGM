# Bad Dream Coma

1. Unpack `game.win` from `romfs`
2. Open `game.win` with `UndertaleModTool`
3. Find `gml_Script__language` Code.
4. Change `0` at the end of `00000: pushi.e 0` to different number that should match language value used in game
Based on `Main_Menu_Language` Game object textures order I'm determining used values
5. Save it and put it in layeredfs

Languages supported via eshop:
- English

Languages originally supported (value)
- Polish (1) // Confirmed working
- French (5)
- Italian (6)
- German (4)
- Spanish (2)
- Russian (3)