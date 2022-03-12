# Permanent Notes

As _notas permanentes_ podem ser entendidas como a camada visível do seu estudo - ou seja, é o resultado da combinação e uso das _notas_ sobre um determinado tema através de um texto [[1]](#1).

Dependendo do contexto e da finalidade, as notas permanentes podem ser utilizadas como produto final, no entanto, dependendo da complexidade do trabalho, as notas permanentes acabam sendo como guia para um novo texto em questão [[2]](#2).

Da mesma forma que as notas, é importante adicionar _metadados_ relevantes em seu cabeçalho, tendo em vista que as reflexões podem ser base de outros estudos e consequentemente você irá estabelecer conexões entre as notas.

## Links a partir de notas

Para facilitar a busca de notas, é utilizado uma extensão do vim [junegun/fzf.vim](https://github.com/junegunn/fzf.vim) associada a um _snippet_ [[3]](#3) para que seja possível:

1. A partir de uma janela do vim, efetuar buscas em notas no repositório
1. Capturar o nome da nota e seu caminho completo para que seja possível estabelecer links

Depois de instalada, é necessário adicionar os seguintes códigos em seu `~.vimrc` :

```vimscript
""" FZF Handler
" References: 
" https://www.edwinwenink.xyz/posts/48-vim_fast_creating_and_linking_notes/

function! HandleFZF(file)
  let filename = fnameescape(a:file)
  let filename_wo_timestamp = fnameescape(fnamemodify(a:file, ":t:s/^[0-9]*_//"))
  let mdlink = "[ ".filename_wo_timestamp." ]( ".filename." )"
  put=mdlink
endfunction

command! -nargs=1 HandleFZF :call HandleFZF(<f-args>)
nnoremap <leader>fzf :call fzf#run({'sink': 'HandleFZF'})<CR>

```
Este snippet `\fzf` quando executado no modo padrão do vim  permite a busca de uma nota através do `fzf` e a captura de seu link no formato do markdown. Isso poupa o trabalho de trocar de janela ou ficar realizando buscas no seu diretório de notas além de formatar o caminho do arquivo de forma automática.

É importante ressaltar que para fazer uma busca recursiva em toda a árvore do seu repositório, é necessário que você esteja na raiz. Recomenda-se iniciar o VIM na raiz da base de conhecimento.


## Referencias

#### [1] : https://zk.zettel.page/types-of-notes

#### [2] : https://zettelkasten.de/posts/field-report-4-what-i-learned-writing-thesis-with-zettelkasten/
 

#### [3] : Ver resposta do comentário do usuário Fernando na thread: [https://www.edwinwenink.xyz/posts/48-vim_fast_creating_and_linking_notes/](https://www.edwinwenink.xyz/posts/48-vim_fast_creating_and_linking_notes/) 
