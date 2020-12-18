# FLiNSGM
Force Language in Nintendo Switch Games Methodology repo

Tools I'm using:
- IDA Pro [for 32-bit apps and some 64-bit hard cases that cannot be done via standard methods in Ghidra (like decompiling 300kB of instructions in one window faster and using much less RAM (40GB was not enough for Ghidra while IDA never passed 8GB usage)]
- Ghidra https://ghidra-sre.org/
- UnityEX https://forum.zoneofgames.ru/topic/36240-unityex/
- hactool https://github.com/SciresM/hactool
- nxdumptool https://github.com/DarkMatterCore/nxdumptool
- UnrealPak (whole tutorial: https://gbatemp.net/threads/how-to-unpack-and-repack-unreal-engine-4-files.531784/)
- HxD https://mh-nexus.de/en/hxd/
- Ghidra Switch Loader https://github.com/Adubbz/Ghidra-Switch-Loader
- nxo64.py https://github.com/reswitched/loaders/blob/master/nxo64.py
- Il2CppDumper https://github.com/Perfare/Il2CppDumper
- Notepad++ https://notepad-plus-plus.org/downloads/
- OpenOffice calc (last time I have checked Excel had issues with parsing tsv while OpenOffice calc works fine)
- UndertaleModTool https://github.com/krzys-h/UndertaleModTool

Documentation:
- Unity `SystemLanguage` enum https://github.com/Unity-Technologies/UnityCsReference/blob/eb7074d546a9f957e9bde0419d3a34beb2946f96/Runtime/Export/BaseClass.cs#L130-L221
