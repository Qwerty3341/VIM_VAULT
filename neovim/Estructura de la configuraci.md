Se hace el archivo `~/.config/nvim/init.lua`

La estructura va a así para la configuración
```vim
.
├── init.lua
├── lua
│   ├── config
│   │   ├── autocmds.lua
│   │   ├── keymaps.lua
│   │   ├── lazy.lua
│   │   └── options.lua
│   └── plugins
```
O
```vim 
~/.config/nvim/
├── init.lua
└── lua/
    ├── options.lua
    ├── keymaps.lua
    └── plugins.lua
```

Se puede usar una distribución como LazyVim que ya configura bastantes cosas manualmente