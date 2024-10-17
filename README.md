# Explicação dos exercícios 6 e 7 da aula 12
_por Diego Rockenbach_
## Instalação local do Prolog com VSCode
Há um pequeno processo de setup para ser possível programar localmente em Prolog através da IDE VSCode, então vou passar brevemente sobre esses passos a seguir.
- [Instalar o SWI-Prolog](https://www.swi-prolog.org/download/stable)

Esse link havia sido passado pra nós na aula 11. ~~Podem ignorar os avisos de vírus.~~

Tenha certeza de durante a instalação marcar a opção de adicionar o SWI-Prolog ao PATH do sistema, isso facilita a chamada dele pelo terminal do VSCode.

- Instalar a extensão de Prolog no VSCode

E pronto! Sempre que quiser testar um arquivo é só ir no diretório que está com o arquivo em questão, abrir o terminal integrado do VSCode e digitar `swipl` para abrir o SWI-Prolog, e então digitar no terminal `consult("[FILENAME]").`, se atentando aos espaços e ao ponto no final da instrução.

> Para sair do terminal _swipl_ basta usar o comando ``halt.``.

## Explicação da resolução dos exercícios 6 e 7

Os exercícios 6 e 7 da aula 12 consistiam em algumas consultas simples usando Prolog, e a resolução que eu cheguei (uma das muitas possíveis) foram as seguintes:

### 6) Há quantos anos foi lançado o filme big_fish?

``yearSubtraction(AnoAtual,AnoBigFish,Res) :- Res is AnoAtual-AnoBigFish.``

Basta procurar o filme Big Fish no Google para descobrir que seu ano de lançamento foi 2003, mas como expressar isso usando Prolog?

O símbolo `:-` usado acima, nessa questão funciona como nada mais do que um separador da função aritmética, sendo a parte em sua esquerda a declaração e em sua direita a função em si. Sendo assim, para saber a quantos anos o filme Big Fish lançou basta subtrair o ano em que nos encontramos (2024) do seu ano de lançamento (2003), e isto será o resultado. Igualmente importante é o operador `is` usado na função: é ele quem diz que isto se trata de uma função aritmética e não uma definição de regras, sem execução de cálculos.

### 7) O ator liam_neeson é um ator de comédia?

```
genero(adamSandler, comedia).
genero(liamNeeson, acao).
genero(liamNeeson, suspense).
genero(jimCarrey, comedia).
genero(jasonMomoa, acao).
genero(jasonMomoa, drama).
```

A lógica do exercício 7 é diferente do exercício 6, pois não estamos mais tratando de resoluções matemáticas, e sim de definições de predicados. Assim, eu defini como fato o gênero mais proeminente da carreira de diversos atores, e então podemos consultar das mais diversas formas isso através do Prolog.

## Principais dificuldades encontradas nos exercícios

- O ``.`` ao final de cada linha.

Não é uma sintaxe muito comum, sendo o esperado finalizar a linha com ``;``, então é normal essa confusão de início.

- Pensar em "o que se quer obter, não como obter".

Prolog não se trata de uma linguagem imperativa, nas quais estamos acostumar a programar exatamente como resolver determinado problema. Na maioria dos casos usando Prolog, iremos escrever um conjunto de fatos e regras (assim como no exercício 7) para então depois obter novas informações a partir do entrelaçar e consulta dos fatos e regras inseridos.

- _Case Sensitive_ em variáveis.

A primeira letra de uma variável em Prolog importa muito, pois é ela quem define o que aquela "variável" de fato será:
Variáveis que iniciam com letras **minúsculas** serão interpretadas como _átomos_, ou valores absolutos. Assim, é impossível alterar seu valor durante o programa. Em contraponto, variáveis que iniciam com letras **maiúsculas** serão interpretadas como variáveis de fato.

### Material usado

> [Instalação de Prolog no Windows VSCode](https://www.youtube.com/watch?v=ThCV1-x8UAw)

> [Introdução a programação em Prolog](https://dcm.ffclrp.usp.br/~augusto/teaching/ia/IA-Prolog-Introducao-Tutorial.pdf)

> Slides da matéria

> Ferramentas IA
