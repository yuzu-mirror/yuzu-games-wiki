# Yuzu Game Patches

Patches should follow the format:
- Path: `<title_id>/<patch_name>` as root folder, where title_id is uppercase hexadecimal
- Within <patch_name>, there can be all of the folders that would go in a mod folder in yuzu (romfs, exefs, etc.)
- Additionally in <patch_name> there should be a patch.dat file:

```
    title = ""
    description = ""
    author = ""
    types = []
```

where types contains any of:
- "LayeredFS"
- "LayeredExeFS"
- "IPS"
- "IPSwitch"

if the patch uses that feature