# Fork

The fork changes the `hhea_ascent` computation so that 2 vertically aligned UILabels, one containing the original font and one containing the one modified by the script, overlap perfectly.

# Debug with VSCode

1. Install python extensions
2. Add `main()` at the end of _lib/fontline/app.py_ 
2. Create the following _launch.json_

```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: Current File (Integrated Terminal)",
            "type": "python",
            "request": "launch",
            "program": "lib/fontline/app.py",
            "cwd": "${workspaceRoot}",
            "env": {"PYTHONPATH": "${workspaceRoot}"},
            "console": "integratedTerminal",
            "args": ["percent",
                     "50",
                     "path_to_font.otf"]
        }
    ]
}
```

# Font rename

One can use fontforge (`brew install fontforge`) if a font rename is required `fontforge --script script.pe fontname.otf` 

### script.pe

```
Open($1)
SetFontNames($1:r,$1:r,$1:r)
Generate($1:r + ".otf")
```