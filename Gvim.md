App gráfica de vim que soporta plugins 

Con `coc.nvim` puede tener este error:
```sh
[coc.nvim] "node" is not executable
```

Para solucionarlo se hace el archivo `.gvimrc` y se coloca lo siguiente:
```sh
let $PATH .= ':/usr/bin:/usr/local/bin'
let $PATH .= ':' . expand('~/.nvm/versions/node/*/bin')
```