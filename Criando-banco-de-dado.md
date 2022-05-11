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

<!-- Realizando cadastro -->

    #### Cadastrando cursos

    ```sql
    INSERT INTO cursos (titulo, carga_horaria, professor_id)
    VALUES ('Front-End', 40, 1, NULL);
           ('Back-End', 80, 2, NULL);
           ('UX/UI', 30, 3, NULL);
           ('Figma', 10, 4, NULL);
           ('Redes de Computadores', 100, 5, NULL);
    ```

        ```sql
    INSERT INTO cursos (titulo, carga_horaria) VALUES 
    ('Front-End', 40, 1),
    ('Back-End', 80, 2),
    ('UX/UI', 30, 3),
    ('Figma', 10, 4),
    ('Redes de Computadores', 100, 5);
    ```

    INSERT INTO cursos (titulo, carga_horaria) VALUES ('Front-End', 40),('Back-End', 80),('UX/UI', 30),('Figma', 10),('Redes de Computadores', 100);

    
    INSERT INTO cursos (nome, area_atuacao, curso_id) VALUES 
    ('Jon Oliver', "Infra", 25),
    ('Lemmy Kilmister', "Desenvolvimento", 22),
    ('Neil Peart', "Design", 23),
    ('Ozzy Osbourne', "Design", 24),
    ('David Gilmour', "Infra", 25);
    ```


    INSERT INTO cursos (nome, data_nascimento, nota1, nota2, curso_id) VALUES 
    ('Albert', "1992-02-06", 8, 7, 25),
    ('Lemmy Kilmister', "Desenvolvimento", 22),
    ('Neil Peart', "Design", 23),
    ('Ozzy Osbourne', "Design", 24),
    ('David Gilmour', "Infra", 25);


   
    -- Criando comando de consulta

-- alunos e nascimento antes 2009
1) Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

    SELECT * FROM alunos WHERE data_nascimento < '2009-01-01';

    [![An old rock in the desert](modelagem-banco.png "Shiprock, New Mexico by Beau Rogers")]

2) Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

    SELECT nome, ROUND(AVG(nota1 + nota2), 2) FROM alunos GROUP BY nome;

3) Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

    SELECT titulo, carga_horaria, ROUND(carga_horaria * 0.25) FROM cursos ORDER BY titulo;