Craindo tabela de dados

<!-- Criando tabelas -->
```sql
CREATE TABLE cursos (
    id INT NOT NULL AUTO_INCREMENT,
    titulo VARCHAR(30) NOT NULL,
    carga_horaria TINYINT NOT NULL,
    PRIMARY KEY (id)
);
```	

```sql	
CREATE TABLE professores (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(50) NOT NULL,
    area_atuacao ENUM('Design', 'Desenvolvimento', 'Infra') NOT NULL,
    curso_id INT NOT NULL
);
```

```sql
CREATE TABLE alunos (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(50) NOT NULL,
    data_nascimento DATE NOT NULL,
    nota1 DECIMAL(4,2) NOT NULL,
    nota2 DECIMAL(4,2) NOT NULL,
    curso_id INT NOT NULL
);
```	