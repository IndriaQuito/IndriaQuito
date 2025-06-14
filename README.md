## Sistema de Cadastro de Alunos e Treinos - Academia 4Life

Este projeto é uma aplicação Java básica com persistência de dados em banco de dados MySQL, desenvolvida para gerenciar o cadastro de **alunos** e seus respectivos **treinos** em uma academia. A interface é baseada em linha de comando (CLI).

## 📋 Funcionalidades

- Cadastrar alunos com as informações:
  - Nome
  - Data de nascimento
  - E-mail
  - CPF
  - Telefone
    
- Cadastrar treinos com as informações:
  - ID do aluno
  - Nome do exercício
  - Número de séries
  - Número de repetições

- Consultar, listar e gerenciar dados (dependendo de futuras implementações)

## 📦 Estrutura do Projeto


## 🛠️ Tecnologias Utilizadas

- Java 8+
- JDBC
- MySQL
- 

## 🗃️ Estrutura do Banco de Dados

### Tabela `alunos`

```sql
CREATE TABLE alunos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    data_nascimento DATE,
    email VARCHAR(100),
    cpf VARCHAR(14),
    telefone VARCHAR(20)
);


CREATE TABLE treinos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    id_aluno INT,
    nome_exercicio VARCHAR(100),
    series INT,
    repeticoes INT,
    FOREIGN KEY (id_aluno) REFERENCES alunos(id)
);

