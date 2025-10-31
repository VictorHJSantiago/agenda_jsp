<div align="center">

📚 Agenda Estudantil (JSP)
Um sistema web para gestão de alunos, professores e atividades acadêmicas.

<img alt="Status do Projeto" src="https://img.shields.io/badge/Status-Completo-brightgreen.svg"> <img alt="Linguagem" src="https://img.shields.io/badge/Linguagem-Java%20(JSP)-orange?style=flat&logo=java"> </p>

</div>

---------------------------------------------------------------------------------------------------
🚀 Sobre o Projeto
O agenda_jsp é um sistema de agenda estudantil focado no ambiente acadêmico. Desenvolvido inteiramente com JavaServer Pages (JSP), ele permite o registo e a gestão centralizada de utilizadores (professores e alunos) e das suas respetivas atividades.

---------------------------------------------------------------------------------------------------
✨ Funcionalidades
O sistema gira em torno de três pilares principais:

👨‍🏫 Gestão de Professores: Permite o registo de novos professores no sistema.

🎓 Gestão de Alunos: Permite o registo de novos alunos.

📝 Gestão de Atividades: Permite o registo e a associação de atividades aos alunos e professores.

---------------------------------------------------------------------------------------------------
🛠️ Tecnologias Utilizadas
A pilha de tecnologia principal para este projeto é:
1. JavaServer Pages (JSP)
2. Java (Servlets)
3. HTML/CSS
4. Servidor de Aplicação (Ex: Apache Tomcat)
5. Banco de Dados SQL (Ex: MySQL, PostgreSQL)

---------------------------------------------------------------------------------------------------
⚙️ Como Executar o Projeto (Exemplo)
Como este é um projeto JSP, ele precisa ser executado num servidor de aplicação Java (como o Apache Tomcat) e, provavelmente, requer um banco de dados.
1. Clone o repositório
git clone [URL_DO_SEU_REPOSITORIO]

2. Configuração do Banco de Dados
Importe o script database.sql (se fornecido) para o seu SGBD (Ex: MySQL, PostgreSQL).
Localize o ficheiro de configuração da conexão (ex: Conexao.java ou config.properties).
Altere as credenciais (URL, USUÁRIO, SENHA) para corresponder às do seu ambiente.

3. Configuração do Servidor
Certifique-se de que tem um servidor de aplicação como o Apache Tomcat instalado.
Compile o projeto (se estiver a usar Maven ou Gradle, use mvn install ou gradle build).
Deploy da Aplicação
Copie o ficheiro .war gerado (da pasta target/ ou build/libs/) para a pasta webapps do seu Apache Tomcat.
Inicie o servidor Tomcat.
Aceder à Aplicação
Abra o seu navegador e aceda a: http://localhost:8080/agenda_jsp (ou o nome do contexto do seu projeto).

---------------------------------------------------------------------------------------------------
🗃️ Estrutura da Base de Dados (Sugestão)
Abaixo está uma estrutura de tabelas provável para este tipo de sistema. (Deverá adaptar com base nos ficheiros .sql ou nas classes de modelo do seu projeto).

SQL CODE
-- Tabela para os Professores
CREATE TABLE professores (
    id_professor INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(255) NOT NULL,
    email VARCHAR(100) UNIQUE,
    senha VARCHAR(100)
);

-- Tabela para os Alunos
CREATE TABLE alunos (
    id_aluno INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(255) NOT NULL,
    email VARCHAR(100) UNIQUE,
    senha VARCHAR(100)
);

-- Tabela para as Atividades
CREATE TABLE atividades (
    id_atividade INT PRIMARY KEY AUTO_INCREMENT,
    descricao TEXT NOT NULL,
    data_entrega DATE,
    id_professor_resp INT,
    id_aluno_atrib INT,
    FOREIGN KEY (id_professor_resp) REFERENCES professores(id_professor),
    FOREIGN KEY (id_aluno_atrib) REFERENCES alunos(id_aluno)
);
