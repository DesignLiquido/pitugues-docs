# Contribuindo

Qualquer pessoa pode sugerir melhoramentos para a linguagem ou correções de bugs. Uma recomendação é abrir uma issue no GitHub antes, para colher a opinião da comunidade e evitar rejeições de contribuições.

Seguimos o padrão do GitHub para modificações. Modificações são feitas por meio de Pull Requests, que nos mostram quais partes do código mudaram da versão atual para a proposta de modificação.

Havendo aprovação dos mantenedores do projeto, juntamos a modificação ao código atual (merge) e lançamos novas versões de tempos em tempos.

## Quer contribuir, mas não se sente a vontade? 
Você tem vontade de contribuir, mas não se sente à vontade em abrir issues, PRs ou fazer perguntas publicamente?

* Você pode nos contatar através do [grupo no Discord](https://discord.gg/4tBxWSSbdV).

## Primeira Contribuição 
Como fazer sua primeira contribuição:
1. [Crie uma Conta no GitHub](#1-crie-uma-conta-no-github)
2. [Encontre uma Issue para trabalhar](#2-encontre-uma-issue-para-trabalhar)
3. [Ou Crie uma Issue](#3-ou-crie-uma-issue)
4. [Instale o Git](#4-instale-o-git)
5. [Faça um Fork do Projeto](#5-faça-um-fork-do-projeto)
6. [Clone o seu Fork](#6-clone-o-seu-fork)
7. [Crie uma Nova Branch](#7-crie-uma-nova-branch)
8. [Pré-requisitos](#8-pré-requisitos)
9. [Estrutura do Projeto](#9-estrutura-do-projeto)
10. [Faça sua Contribuição](#10-faça-sua-contribuição)
11. [Testes](#11-testes)
12. [Commit & Pull Request (PR)](#12-commit--pull-request-pr)

### 1. Crie uma Conta no GitHub
Certifique-se de ter [uma conta no GitHub](https://github.com/) e de estar com a sessão iniciada.

Caso não tenha uma conta, siga os passos de como [criar de uma conta pessoal no GitHub](https://github-essentials.cumbuca.dev/dia-5-contas-e-planos/criacao-de-uma-conta-pessoal-no-github).

**DICA**: É fundamental entender como Git e GitHub funcionam. Recomendamos o [e-book _Git e GitHub para Humanos_ da Cumbuca.dev](https://git-e-github.para-humanos.cumbuca.dev/) como uma introdução.

### 2. Encontre uma Issue para trabalhar
Vá até a [página de issues de Delégua](https://github.com/DesignLiquido/delegua/issues) e encontre uma issue que gostaria de trabalhar, que ainda não tenha sido atribuída a alguém e que contenha a notação `[Pituguês]` no título da issue, ou que esteja marcada com o label `pituguês`.

**Quer assumir a Issue e não sabe como?** No e-book _Git e GitHub para Humanos_ há disponível este [tutorial para atribuição de issues](https://git-e-github.para-humanos.cumbuca.dev/8.-issues-no-github/8.4-atribuindo-uma-issue-no-github).

### 3. Ou Crie uma Issue
Se você não encontrar uma Issue que queira trabalhar dentre as já existentes, você pode [criar uma Issue no repositório de Delégua](https://github.com/DesignLiquido/delegua/issues/new/choose), descrevendo a implementação que deseja fazer e atribuí-la a si mesmo.

A issue deve conter a notação `[Pituguês]` no início do título e ter o label `pituguês` indicado.

Para informações mais detalhadas sobre a criação de issues, você pode visitar [este tutorial](https://git-e-github.para-humanos.cumbuca.dev/8.-issues-no-github/8.2-criando-uma-issue-no-github).

### 4. Instale o Git
Certifique-se de ter o git instalado e, caso não tenha, você pode seguir o passo a passo deste [tutorial de instalção do git](https://git-e-github.para-humanos.cumbuca.dev/2.-fundamentos-de-controle-de-versao-e-git/2.4-instalando-o-git),

### 5. Faça um Fork do Projeto
Recomenda-se fazer um _fork_ do projeto para sua conta. Você pode consultar este [tutorial do GitHub sobre Fork](https://docs.github.com/pt/get-started/exploring-projects-on-github/contributing-to-a-project).

### 6. Clone o seu Fork
[Clone](https://docs.github.com/pt/repositories/creating-and-managing-repositories/cloning-a-repository) o seu fork localmente.

### 7. Crie uma Nova Branch
Em sua máquina, navegue até o repositório clonado:
```
cd delegua
```

Crie uma nova branch com o título da issue que você irá trabalhar através do comando:
```
git checkout -b <numero_da_issue>
```

Exemplo:
```
git checkout -b 386
Switched to a new branch '386'
```
### 8. Pré-requisitos
* Baixe e instale o [Node.js](https://nodejs.org/pt/download) no seu dispositivo
* Utilizamos o gerenciador de pacotes [Yarn](https://yarnpkg.com/) e recomendamos sua instalação através da linha de comando:
```
npm install -g yarn
```
E, para fazer o download e instalação dos pacotes necessários, dentro do diretório raiz, executar:
```
yarn
```

### 9. Estrutura Base do Projeto

Pituguês é um dialeto de programação que existe dentro do código fonte de Delégua. Ele é inspirado na linguagem Python e busca trazer seus elementos para a língua portuguesa, tornando a programação mais acessível para os falantes lusófonos. 

A arquitetura da linguagem é dividida entre:
 * Lexador: é responsável por ler o código-fonte, caractere por caractere, reconhecendo os padrões textuais do código e tranformá-lo em unidades menores, que podemos chamá-las de tokens ou símbolos.
 * Avaliador Sintático: após identificar os símbolos da linguagem no lexador, temos o Avaliador Sintático cuja função é verificar se os símbolos/tokens da linguagem estão organizados de forma lógica para execução das instruções.
 * Interpretador: executa a linguagem em tempo real, após receber a validaçao do Avaliador Sintático.

Está indicado abaixo, entre `**`, a localização dos arquivos destinados do lexador, avaliador sintático e interpretador em é empregada a lógica para composição e execução do Pituguês.

Obs.: o Pituguês utiliza o mesmo Interpretador que a linguagem Delégua.

```md
├── delegua/
│ ├── .github
│ ├── .vscode
│ ├── exemplos
│ ├── fontes
│ │ ├── analisador-semantico
│ │ ├── avaliador-sintatico
│ │ │ ├── dialetos
│ │ │ │ **avaliador-sintatico-pitugues.ts**
│ │ ├── bibliotecas
│ │ ├── construtos
│ │ ├── declaracoes
│ │ ├── depuracao
│ │ ├── excecoes
│ │ ├── formatadores
│ │ ├── geracao-identificadores
│ │ ├── interfaces
│ │ ├── interpretador
│ │ │ **interpretador.ts**
│ │ ├── lexador
│ │ │ ├── dialetos
│ │ │ │ **lexador-pitugues.ts**
│ │ ├── tipos-de-dados
│ │ ├── tipos-de-simbolos
│ │ ├── tradutores 
│ │ index.ts
│ │ inferenciador.ts
│ │ informacao-elemento-sintatico.ts
│ │ README.md
│ │ tipo-dados-elementar.ts
│ ├── gramaticas
│ ├── recursos
│ ├── testes
│ │ ├── avaliador-sintatico
│ │ ├── calango
│ │ ├── egua-classico
│ │ ├── formatadores
│ │ ├── guarani
│ │ ├── interpretador
│ │ ├── lexador
│ │ ├── pitugues
│ │ │ **avaliador-sintatico.test.ts**
│ │ │ **interpretador.test.ts**
│ │ │ **lexador.test.ts** 
│ │ ├── portugol-ipt
│ │ ├── primitivas
│ │ ├── tradutores
│ │ analisador-semantico.test.ts
│ │ biblioteca-global.test.ts
│ .editorconfig
│ .gitignore
│ .prettierrc
│ .release-it.json
│ CODE_OF_CONDUCT.md
│ CONTRIBUINDO.md
│ CONTRIBUTING.md
│ LICENSE
│ LICENSE.pt.txt
│ README.md
│ SECURYTI.md
│ babel.config.js
│ eslint.config.js
│ import_map.json
│ jest.config.ts
│ package.json
│ tsconfig.json
│ yarn.lock
```

Para conhecer com mais profundidade a arquitetura da linguagem, recomendamos [esta playlist](https://www.youtube.com/playlist?list=PL6y10dwsUMhpnsBj_f3Us-JkRDBwEnq8O) produzida pela Design Líquido. 

### 10. Faça sua Contribuição
Concluída as etapas anteriores, você pode modificar o código para adicionar a sua contribuição nos arquivos destinados ao Pituguês.

### 11. Testes

Após implementar sua contribuição no código, você pode **criar testes unitários** antes de enviar seu PR.

O testes são escritos utilizando o padrão da [biblioteca Jest para testes](https://jestjs.io/) e são dividos em duas seções:
* Cenários de sucesso
* Cenários de falha

Você pode incluir testes em ambas seções.

O diretório de testes para Pituguês também está indicado na seção de [estrutura do projeto](#9-estrutura-do-projeto) e são os arquivos para testes são divididos entre testes para o lexador, avaliador sintático e interpretador.

### Estrutura dos testes

1. Lexador
Busca-se identificar se os símbolos (tokens) esperados são identificador pelo lexador. 

Exemplo dentro da seção `Cenários de Sucesso`:
```javascript
it('Sucesso - Olá mundo', () => {
    const resultado = lexador.mapear(
        ["escreva('Olá mundo')"],
        -1
    );

    expect(resultado).toBeTruthy();
    expect(resultado.simbolos).toHaveLength(4);
    expect(resultado.simbolos).toEqual(
        expect.arrayContaining([
            expect.objectContaining({ tipo: 'ESCREVA' }),
            expect.objectContaining({ tipo: 'PARENTESE_ESQUERDO' }),
            expect.objectContaining({ tipo: 'TEXTO' }),
            expect.objectContaining({ tipo: 'PARENTESE_DIREITO' }),
        ])
    );
});
```

Exemplo dentro da seção de `Cenários de Falha`:
```javascript
it('Falha léxica - texto sem fim', () => {
    const resultado = lexador.mapear(
        ['"texto sem fim'],
        -1
    );
    expect(resultado.simbolos).toHaveLength(0);
    expect(resultado.erros).toHaveLength(1);
});
```

2. Avaliador Sintático
Nestes testes, deverão constar o total de declarações retornadas, como no seguinte exemplo:
```javascript
it('Atribuição com soma', () => {
    const retornoLexador = lexador.mapear(
        [
            'imprima(2 + 2)',
            'var a = 2',
            'imprima(a += 2)',
            'imprima(a)'
        ], -1
    );
    const retornoAvaliadorSintatico =
        avaliadorSintatico.analisar(retornoLexador, -1);

    expect(retornoAvaliadorSintatico).toBeTruthy();
    expect(retornoAvaliadorSintatico.declaracoes).toHaveLength(4);
});
```

3. Interpretador
Buscamos que o atributo `erros` do interpretador retorne com o valor `zero` e, para alguns tipos de testes, deve-se retornar as saídas, como o exemplo abaixo:
```javascript
it('Uso de funções de ordem superior', async () => {
    const codigo = [
        "var vetor = [1, 2, 3]",
        "var fn = funcao(valor):",
        "    retorna valor * 2",
        "escreva(mapear(vetor, fn))"
    ];
    const retornoLexador = lexador.mapear(codigo, -1);
    const retornoAvaliadorSintatico = avaliadorSintatico.analisar(retornoLexador, -1);

    const retornoInterpretador = await interpretador.interpretar(retornoAvaliadorSintatico.declaracoes);

    expect(retornoInterpretador.erros).toHaveLength(0);
    expect(_saidas).toHaveLength(1);
    expect(_saidas[0]).toBe('[2, 4, 6]');
});
```

### Verificação de Testes - Testes Automatizados
Antes de enviar sua contribuição, verifique se suas modificações não causaram interferência nas funcionalidades existentes. Para isto, temos o testes automatizados que são executados a partir do comando:
```
yarn testes-unitarios
```


### 12. Commit & Pull Request (PR)

No diretório raiz, em um terminal de linha de comando, faça um commit executando passos:

Verifique a branch em que você está:
```
git branch --show-current
```

Adicione suas alterações para a stagin area:
```
git add .
```

Faça o commit delas:
```
git commit -m "<mensagem_de_commit>"
```

Envie suas alterações para o GitHub via push:
```
git push --set-upstream origin <issue_number>
```

Após enviar suas alterações para o repositório remoto no GitHub, navegue até o [repositório no GitHub](https://github.com/DesignLiquido/delegua) e você poderá abrir seu Pull Request (PR) como indicado [neste tutorial do ebook Git e GitHub para Humanos](https://git-e-github.para-humanos.cumbuca.dev/10.-pull-requests-no-github/10.3-criando-um-pull-request-no-github).


#### Forneça uma descrição detalhada do PR
* Inclua uma descrição completa no seu PR para explicar:
  * O que foi feito (ex.: adicionou uma nova função, corrigiu um bug).
  * Por que foi feito (ex.: para resolver uma issue específica ou melhorar o desempenho).
  * Quais problemas foram resolvidos ou melhorias aplicadas (ex.: referencie a issue ou descreva a melhoria).

* Benefícios:
  * Descrições detalhadas agilizam o processo de revisão ao fornecer contexto.
  * Ajudam futuros mantenedores a entender o propósito e o histórico do código.

#### Vincule o PR à Issue Relacionada
* Referencie a issue que seu PR resolve usando palavras-chave como Closes #474 ou Fixes #474 na descrição do PR. Isso fecha a issue automaticamente quando o PR for mesclado.
* Exemplo: Closes #474
* Benefícios:
  * Vincular issues mantém o repositório organizado e garante o rastreamento de tarefas.
  * Automatiza o fechamento de issues, reduzindo trabalho manual para mantenedores.

Para mais detalhes, consulte a [documentação do GitHub sobre fechamento automático de issues](https://docs.github.com/pt/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).
