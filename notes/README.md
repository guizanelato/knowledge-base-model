# Notes

Uma possível interpretação para _notas_ a partir do modelo Zettelkasten [[1]](#\[1\]), é aquela que pensa uma nota como uma forma de explicar o ponto de vista de uma fonte de informação sobre os seus termos. Um arquivo de nota deve então conter informações como uma espécie de resumo sobre uma fonte, e que este resumo seja capaz de ser utilizado como base de apoio para outros projetos. 

Há também quem entenda que as notas são uma forma de consolidação de conhecimento, a qual utilizamos o texto em questão como um exercício de explicação sobre uma determinada fonte de informação a fim de reforçar a aprendizagem e deixar em aberto novas conexões [[2]](#2) .

Para fins deste repositório, entende-se  **nota** como a primeira etapa de um estudo, seja este estudo de qualquer natureza, com a finalidade de reter conhecimento a partir de uma determinada fonte de informação com uma produção de um texto que explique as ideias principais e que denote o ponto de vista do autor em questão. 

**Em resumo, é possível entender como um esforço de explicar com suas próprias palavras o resultado de uma leitura ou exercício sobre um determinado tema.**

Para que este esforço tenha longevidade, é importante que essa nota seja:

1. Organizada de forma tal que sua busca seja facilitada a partir de utilitários como `grep/fzf`
1. Que seja simples identificar do que a nota se trata, a partir de palavras-chave no formato de uso do `ctags`; além de servir como referência futura para outros tipos de notas
1. Que cada nota tenha um identificador único como prefixo de seu nome, a fim de garantir que notas sobre assuntos similares e até mesmo com mesmo nome sejam persistidas sem o risco de sobreposição.


No que se refere ao primeiro item, o diretório para essa primeira camada de estudo será `./notes`. 

Para o segundo item, utilizaremos o seguinte cabeçalho no formato de comentário HTML (dado sua característica de interferir pouco nos utilitários de conversão de formato como o [pandoc](https://pandoc.org)) :


```markdown
<!--
   Data: YYYY-MM-DD
   Título: <Título da fonte>
   Tags: @machine-learning @ia
   autor: <Autor>
   fonte: <link para a fonte/endereço local do arquivo sobre a fonte>
-->

# Título 

....

```

Sobre o último item em questão, para criar um identificador único dos arquivos, utilizaremos um `snippet` do VIM capaz de gerar um novo arquivo no _buffer_ com o seguinte formato de nome  `YYYYMMDDhhmmss\_nome-do-arquivo.md`. Para tal, adicione em seu `.vimrc` a seguinte linha de comando:

```
command! -nargs=1 NewNote :execute ":e" . strftime("%Y%m%d%H%M") . "_<args>.md"
```

Com isso, uma nova opção de comando aparecerá quando utilizar a combinação `<ESC>+:` - o comando `NewNote` que espera um argumento , que no caso é o próprio nome do arquivo. Caso queira por exemplo criar uma nota com nome `distancia-euclidiana` podemos executar o comando a seguir, depois de iniciar a sequência `<ESC>+:` :

```
:NewNote distancia-euclidiana
```

Note que ao apertar `<ENTER>`, o VIM retornará a seguinte mensagem:

```
"202203121550_distancia-euclidiana.md" [Novo arquivo]"  
```

> É importante destacar que o ato de adicionar uma nota com o comando `NewNote` não implica que o arquivo esteja salvo em disco. Como informado anteriormente, o VIM cria esse aquivo no _buffer_, e este precisa ser salvo em disco através dos comandos de salvamento do VIM tais como `:w`, `:x` ou até mesmo através da sequência `<SHIFT>+ZZ`.

## Referências

#### [1] : https://zettelkasten.de/posts/overview/#the-introduction-to-the-zettelkasten-method

#### [2] : https://www.edwinwenink.xyz/posts/59-writing_not_collecting/


