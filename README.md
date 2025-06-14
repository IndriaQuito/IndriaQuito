## Sistema de Cadastro de Alunos e Treinos - Academia 4Life

Este projeto é uma aplicação Java básica com persistência de dados em banco de dados MySQL, desenvolvida para gerenciar o cadastro de **alunos** e seus respectivos **treinos** em uma academia. A interface é baseada em linha de comando (CLI).

## 📚 Descrição Geral

O sistema Academia 4Life permite à administração de academias:

- Cadastrar, listar, editar e excluir alunos;
- Cadastrar, listar, editar e excluir treinos vinculados a alunos;
- Navegar por menus intuitivos por meio da linha de comando.


## ⚙️ Tecnologias Utilizadas

- Java SE 8+
- JDBC
- MySQL
- IDE Java 
- Terminal para execução CLI

  
## 🚀 Como Executar

1. **Clone o repositório**:

   ```bash
   git clone https://github.com/seuusuario/academia-4life.git

•  Importe o projeto em sua IDE Java.

•  Configure o banco de dados:

•	Crie um banco no MySQL com o script abaixo.

•  Configure a conexão JDBC em ConexaoBD.java:

private static final String URL = "jdbc:mysql://localhost:3306/academia4life";

private static final String USUARIO = "root";

private static final String SENHA = "sua_senha";

Execute a classe Main.java para iniciar a aplicação.




🗄️ Banco de Dados

Script: database/academia4life.sql

create database if not exists academia4life;

use academia4life;

create table if not exists alunos (

    id INT AUTO_INCREMENT PRIMARY KEY,
    
    nome VARCHAR(100) NOT NULL,
    
    data_nascimento DATE NOT NULL,
    
    email VARCHAR(100) NOT NULL,
    
    cpf VARCHAR(14),
    
    telefone VARCHAR(20)
);

create table if not exists treinos (

    id INT AUTO_INCREMENT PRIMARY KEY,
    
    nomeExercicio VARCHAR(100) NOT NULL,
    
    repeticoes INT NOT NULL,
    
    series INT NOT NULL,
    
    id_aluno INT NOT NULL,
    
    FOREIGN KEY (id_aluno) REFERENCES alunos(id) ON DELETE CASCADE
);

📦 Classes e Responsabilidades:

🔹 Main.java
Interface CLI que exibe menus principais:
•	Menu Aluno: cadastro, listagem, edição, exclusão
•	Menu Treino: cadastro, listagem por aluno, edição, exclusão

🔹 Aluno.java
Entidade com os atributos:
•	id, nome, dataNascimento, email, cpf, telefone

🔹 Treino.java
Entidade com os atributos:
•	id, idAluno, nomeExercicio, series, repeticoes

🔹 AlunoDAO.java
Responsável por operações SQL da tabela alunos.

🔹 TreinoDAO.java
Responsável por operações SQL da tabela treinos.

🔹 ConexaoBD.java
Responsável por fornecer a conexão com o banco MySQL via JDBC.
________________________________________
📁 Exemplo de Uso
======================================
          ACADEMIA 4LIFE              
======================================
1 - Gerenciar Alunos
2 - Gerenciar Treinos
0 - Sair
Escolha uma opcao: 1

=========== MENU ALUNO ============
1 - Cadastrar Aluno
2 - Listar Alunos
3 - Editar Aluno
4 - Excluir Aluno

👨💻 Autor
Desenvolvido por Indria Quito e Cecilia Sartori
________________________________________
📄 Licença
Este projeto está licenciado sob os termos da licença MIT.








