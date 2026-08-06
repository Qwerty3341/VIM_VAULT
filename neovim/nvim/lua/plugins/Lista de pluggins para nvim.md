Cada plugin puede ser un archivo y se definen como tablas de Lua.
```Lua
-- lua/plugins/telescope.lua
return {
  "nvim-telescope/telescope.nvim",
  dependencies = { "nvim-lua/plenary.nvim" },
  keys = {
    { "<leader>ff", "<cmd>Telescope find_files<cr>" },
    { "<leader>fg", "<cmd>Telescope live_grep<cr>" },
  },
  opts = {
    -- opciones del plugin
  },
}
```
## Plugins recomendados
- Blink (autocompletado)
- bufferline (lista de buffers)
- nvim-lspconfig
- mason (gestor de LSPs)
- nvim autopairs (autocompletado de llaves)
- treesitter (resaltado de sintaxis)
- snacks (colección de plugins)


> [!NOTE] Title
> Contents
