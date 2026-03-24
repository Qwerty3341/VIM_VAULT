# En keymaps
```lua
vim.opt.tabstop = 4
vim.opt.shiftwidth = 4
vim.opt.softtabstop = 4
vim.opt.expandtab = false

vim.keymap.set("i", "<S-Tab>", "<C-d>")
vim.keymap.set("n", "<S-Tab>", "<<")
vim.keymap.set("n", "<Tab>", ">>")
vim.keymap.set("v", "<Tab>", ">gv")
vim.keymap.set("v", "<S-Tab>", "<gv")

```
# En options.lua
```lua
vim.keymap.set("n", "<leader>w", ":w<CR>", { desc = "Guardar archivo" })
vim.keymap.set("n", "<leader>q", ":q<CR>", { desc = "Salir" })
```