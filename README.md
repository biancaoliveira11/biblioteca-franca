# Sistema de Gerenciamento de Biblioteca Municipal

Projeto Final – 2º Bimestre
Disciplina: Modelagem de Banco de Dados

## 1. Cenário

### 1.1. Descrição da instituição

O projeto será inspirado na Biblioteca Municipal de Franca, no interior de São Paulo, porém será apresentado em um cenário fictício. Trata-se de uma instituição pública de uso da comunidade, que promove o acesso à leitura, à informação, à cultura e ao conhecimento para a população de Franca.

### 1.2. Problema identificado

A biblioteca enfrenta certas dificuldades em relação ao gerenciamento e à organização do seu acervo:

- Livros que não são encontrados durante a pesquisa no sistema;
- Falta de informações sobre os leitores que pegaram exemplares emprestados e não realizaram a devolução;
- Dificuldade em identificar a quantidade de exemplares disponíveis de cada livro do acervo;
- Dificuldade de acesso ao catálogo on-line de livros, fazendo com que a comunidade precise comparecer presencialmente para verificar os livros disponíveis;
- Dificuldade na localização de livros armazenados em prateleiras incorretas;
- Falta de controle sobre a entrada e a saída dos livros do acervo.

### 1.3. Objetivo do sistema

O projeto tem como objetivo desenvolver um banco de dados relacional para auxiliar no gerenciamento do acervo da Biblioteca Municipal de Franca, facilitando o trabalho dos bibliotecários e demais funcionários, além de beneficiar os leitores e a comunidade que participa das atividades da biblioteca.

**O sistema deverá permitir:**

- Cadastro de novos livros e exemplares;
- Cadastro de leitores;
- Controle de empréstimos e devoluções;
- Consulta de livros pelos bibliotecários e leitores;
- Identificação da disponibilidade e localização dos exemplares;
- Controle da quantidade de exemplares de cada obra;
- Identificação dos leitores com empréstimos pendentes;
- Registro da retirada definitiva de exemplares do acervo.


### 1.4. Entidades e atributos
O sistema será composto por seis entidades principais, responsáveis pelo armazenamento das informações necessárias para o gerenciamento da biblioteca.

#### Livro

- id_livro (chave primária);
- titulo;
- ano_publicacao;
- genero;
- quantidade_exemplares (atributo derivado).

#### Autor

- id_autor (chave primária);
- nome;
- nacionalidade.

#### Leitor

- id_leitor (chave primária);
- nome;
- cpf;
- data_nascimento;
- endereco (atributo composto por rua, número, bairro, cidade e CEP);
- telefone (atributo multivalorado);
- email;
- idade (atributo derivado).

#### Carteirinha

- id_carteirinha (chave primária);
- data_emissao;
- data_validade;
- situacao.

#### Empréstimo

- id_emprestimo (chave primária);
- data_emprestimo;
- data_prevista_devolucao;
- data_devolucao;
- quantidade_renovacoes;
- dias_atraso (atributo derivado).

#### Exemplar

- id_exemplar (chave primária);
- numero_exemplar;
- edicao;
- estante;
- prateleira;
- estado_conservacao;
- situacao;
- data_aquisicao.

#### Classificação dos atributos

| Tipo de atributo | Exemplo |
|---|---|
| Simples | Título do livro |
| Composto | Endereço do leitor |
| Multivalorado | Telefone do leitor |
| Derivado | Idade do leitor |
| Chave primária | ID do leitor |

### 1.5. Regras de negócio e relacionamentos

#### Regras de negócio

- Cada leitor poderá possuir no máximo dois empréstimos ativos simultaneamente, referentes a livros diferentes.
- Cada registro de empréstimo será referente a apenas um exemplar.
- O prazo inicial para devolução será de 30 dias.
- Será permitida apenas uma renovação por empréstimo, acrescentando 15 dias ao prazo de devolução.
- Leitores com empréstimos atrasados não poderão realizar novos empréstimos.
- Cada leitor deverá possuir uma única carteirinha.
- A carteirinha terá validade de dois anos.
- Cada livro será classificado em um único gênero literário.
- Cada livro deverá possuir pelo menos um exemplar cadastrado.
- Edições diferentes de uma mesma obra serão cadastradas como exemplares distintos do mesmo livro.
- Cada livro deverá possuir pelo menos um autor identificado.
- Cada autor cadastrado deverá estar associado a pelo menos um livro.
- Um exemplar não poderá estar emprestado para dois leitores simultaneamente.
- Exemplares perdidos, danificados ou retirados definitivamente do acervo terão sua situação atualizada, preservando o histórico.
- Novos exemplares recebidos pela biblioteca deverão possuir registros próprios.

#### Relacionamentos

| Entidades | Relacionamento | Cardinalidades |
|---|---|---|
| Leitor e Empréstimo | Realiza | 1:N |
| Livro e Exemplar | Possui | 1:N |
| Exemplar e Empréstimo | Participa | 1:N |
| Autor e Livro | Escreve | N:N |
| Leitor e Carteirinha | Possui | 1:1 |

## 2. Modelagem Conceitual

O modelo conceitual foi desenvolvido utilizando a ferramenta
Draw.io, seguindo a notação de Chen.

O Diagrama Entidade-Relacionamento (DER) apresenta as seis
entidades principais do sistema, seus atributos, relacionamentos
e respectivas cardinalidades.

O modelo contempla atributos simples, compostos, multivalorados,
derivados e identificadores, além dos relacionamentos
1:1, 1:N e N:N.

### 2.1. Diagrama Entidade-Relacionamento (DER)

![Modelo Conceitual](diagramas/modelo-conceitual-biblioteca.png)

[Arquivo editável do diagrama](diagramas/modelo-conceitual-biblioteca.drawio)

Em desenvolvimento.

## 3. Modelagem Lógica

Em desenvolvimento.

## 4. Modelagem Física

Em desenvolvimento.

## 5. Dados

Em desenvolvimento.

## 6. CRUD

Em desenvolvimento.

## 7. Relatórios

Em desenvolvimento.
