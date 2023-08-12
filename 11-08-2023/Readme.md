# ARQUITETURA E MODELAGEM DE DADOS 
<h5>Aula 11/08/2023</h5>

<h3>Informações Importantes 🔍</h3>

- Dado - menor particula de uma informação;
- Informação - Dado contextualizado;
- Banco de Dados: Contém dados relacionados a uma necessidade específica;
- Nunca armazenar dados computados;

<h3> SGBD - Sistema Gerenciador de Banco de Dados🧑‍💻</h3>

  - Software responsável por gerenciar o banco de dados
  - Ex.: MySQL, Postegre, Oracle
  - Backup: Cópia de Segurança
  - Restore: Carrega o backup para o DB;
  - Organização de arquivos;
  - Carregamento(loading): Carregamento de dados no DB != restore/backup;
  - Todos os SGBD's possuem transações - é uma coleção de operações que desempenha uma função única dentro de uma aplicação dos sistemas de banco de dados - se uma coisa der errado, e algo der errado (por exemplo, uma falha de sistema) durante a transação, todas as operações serão revertidas para manter a consistência do banco de dados.;
    - Atomicidade: Todas as operações de uma transação precisa ser executada, ou nada executa;
    - Consistência: A consistencia do banco, não deve violar e nem atrapalhar o sistema/banco;
    - Isolamento: Transações não devem interferir em outras transações;
    - Durabilidade: Após a conclusão de uma transação bem-sucedida, os resultados devem ser duráveis, ou seja, permanecer no banco de dados mesmo em caso de falhas do sistema.

