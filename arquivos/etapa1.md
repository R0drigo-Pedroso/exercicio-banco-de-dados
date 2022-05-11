# Exercícios de Banco de Dados - Etapa 1

## Modelagem Lógica e Física

### A. Modelagem Lógica

#### Usando o MySQL Workbench, faça a modelagem lógica de três entidades (tabelas): **cursos**, **professores** e **alunos**.

- A entidade **cursos** deve conter os seguintes campos:

    - Id (inteiro pequeno), não nulo, com chave primária e auto incrementado
    - Título (string com tamanho 30) não nulo
    - Carga horária (inteiro pequeno), não nulo
    - Id do Professor (inteiro pequeno) nulo

- A entidade **professores** deve conter os seguintes campos:    

    - Id (inteiro pequeno), não nulo, com chave primária e auto incrementado
    - Nome (string com tamanho 50) não nulo
    - Área de atuação (uma lista de dados contendo somente as opções *design*, *desenvolvimento*, *infra*) não nulo
    - Id do Curso (inteiro pequeno) não nulo

- A entidade **alunos** deve conter os seguintes campos:    

    - Id (inteiro pequeno), não nulo, com chave primária e auto incrementado
    - Nome (string com tamanho 50) não nulo
    - Data de nascimento (Data) não nulo
    - Primeira nota (decimal tamanho total 4, 2 dígitos depois da vírgula) não nulo
    - Segunda nota (decimal tamanho total 4, 2 dígitos depois da vírgula) não nulo
    - Id do Curso (inteiro pequeno) não nulo

  
#### Crie os relacionamentos de acordo com a cardinalidade indicada a seguir:

- **1 curso tem vários alunos**, portanto será usada a cardinalidade **1:N**. 

*Isso criará um campo chamado curso_id na tabela de alunos. Dica: clique primeiro em alunos e depois em cursos.*

- **1 professor leciona somente 1 curso**, portanto será usada a cardinalidade **1:1**. 

*Isso criará um campo chamado professor_id na tabela cursos. Dica: clique primeiro em cursos e depois em professores.*

- **1 curso é lecionado somente por 1 professor**, portanto será usada a cardinalidade **1:1**. 

*Isso criará um campo chamado curso_id na tabela professores. Dica: clique primeiro em professores e depois em cursos.*

---

### B. Modelagem Física

- Crie um banco de dados chamado **tecinternet_escola_seunome**
- Usando o phpMyAdmin (via interface e/ou códigos SQL), crie a modelagem física de acordo com o que foi feito na modelagem lógica.



