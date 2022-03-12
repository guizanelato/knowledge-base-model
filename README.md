# Knowledge-Base Repo

Repositório modelo para criação de uma base de conhecimento. 

## Como funciona

O fluxo de trabalho pressupõe o mínimo de dependências e é baseado no editor de texto [VIM](https://www.vim.org). 

Em termos de estrutura, a ideia é ter um repositório que seja capaz de conectar registros de estudo a fim de criar uma base de conhecimento através da escrita. Os registros podem ser de natureza diversas:

- fichamentos e/ou notas diretas de uma determinada fonte
- resumos/reflexões de uma determinada fonte
- produtos do estudo sob diversos formatos (blog-posts, capítulos, artigos, etc.)

Para realizar essa conexão, utilizamos recursos próprios do **VIM** além de sua integração com o [universal-ctags](https://github.com/universal-ctags/ctags) - Para maiores informações sobre como instalar e/ou configurar o _universal-ctags_ veja a seção de _Requisitos_.

Os principais atributos nativos do VIM são:

- **vim buffer**
  - Ao abrir qualquer tipo de arquivo dentro de uma sessão do vim, ele cria um buffer com os arquivos que foram utilizados. É possível navegar entre eles, sem que seja necessário ter uma janela aberta, utilizando os comandos `:ls` para ver os arquivos abertos; `: b <nome do arquivo>` para realizar a troca de contexto de buffer em questão.

- **grep**
  - é possível executar comandos de busca com grep através do vimgrep ou até mesmo utilizar o coringa `!grep [opts]`. 

- **tag select**
  - Ao ter uma base de tags preparada através do **ctags** é possível realizar uma busca integrada a partir do comando `: ts <tag>`. O resultado deste comando é uma lista de arquivos os quais foram encontradas as tags. Para acessar é necessário indicar o índice informado no resultado da busca.

- **tab[new|Next|Previous]** 
  - caso queira trabalhar com mais de uma aba dentro do vim, é possível utilizar diversas abas. Utilize quando realmente for necessário pois o _buffer_ pode ser mais ágil.

- **vertical/horizontal split**
  - Caso queira visualizar mais de um arquivo de uma vez em uma mesma janela, utilizando splits horizontais/verticais através do comando `vsplit` ou `hsplit`.

- **snippets**
  - o VIM é customizável ao ponto de executar comandos, criar atalhos, entre outras funcionalidades. Para esse tipo de fluxo de trabalho alguns desses atributos foram adicionados no arquivo de configuração `.vimrc`. 

### Estrutura de Diretórios

Pense neste repositório como uma base universal de notas. É possível utilizá-lo como unidades a partir de uma finalidade (por exemplo a escrita de um livro, dissertação, etc.) ou pensar como um repositório total, contendo todas as suas anotações e reflexões, as quais podem ser utilizadas posteriormente através de referências através de tags. Atualmente a estrutura de diretórios possui o seguinte formato:

```

```

### [C]Tags 

Para identificar tags específicas a partir do _universal c-tags_, é preciso adicionar uma configuração no diretório `ctags.d` . Por convenção, utilizaremos um `@` antes da tag. 

### fzf

O FZF é um utilitário de linha de comando que permite fazer buscas de arquivos de forma rápida e eficiente. 

## Workflow



## Requisitos

Para utilizar desde repositório e de sua estrutura, é recomendável:

1. Ter o vim instalado
1. Ter o universal-ctags instalado
1. Ter o [fzf](https://github.com/junegunn/fzf) instalado.

Em distribuições Linux, esse tipo de instalação é bastante simples utilizando o seu gerenciador de pacotes favorito. No meu caso, utilizo a distribuição Ubuntu, na versão 20.04 e para instalar ambos os pacotes com o **apt** utilizei o seguinte comando:

```
>$ sudo apt install -y vim universal-ctags fzf

```


## Referências

- [Custom Note Tagging System with Ctags and Vim](https://www.edwinwenink.xyz/posts/43-notes_tagging/)
- [VIM notetaking](Building a Note-taking System with Vanilla Vim)
- ["New" Zettelkasten](https://zettelkasten.de/)
- [Zettelkasten](https://niklas-luhmann-archiv.de/bestand/zettelkasten/inhaltsuebersicht#ZK_1_editor_I_45-11)
