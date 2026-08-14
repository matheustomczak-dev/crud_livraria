# crud_livraria

RF1: Cadastrar Livro: o sistema deve permitir cadastrar livros informando titulo, autor e ano de publicação;
RF2: Listar Livros: o sistema deve apresentar todos os livros cadastrados;
RF3: Editar Livros: o sistema deve permitir a alteração de informações de livros já cadastrados;
RF4: Excluir Livros: o sistema deve permitir a exclusão de informações de livros já cadastrados;

(1/2) RNF1: Validação dos Campos: O sistema não deve permitir o cadastro de livros com titulo, autor ou ano vazios.



Introdução
Neste trabalho vou analisar um sistema simples de cadastro de livros feito com PHP e MySQL. O objetivo é entender como os dados são enviados para o banco e como podemos deixar o sistema mais seguro usando Prepared Statements.

O que são Prepared Statements 
Prepared Statements são uma forma mais segura de fazer consultas no banco de dados. Eles permitem separar o comando SQL dos dados fornecidos pelo usuário, evitando que essas informações sejam interpretadas como parte do comando. No PHP, isso é feito usando funções como prepare(), bind_param() e execute().


SQL Injection
SQL Injection é quando alguém consegue inserir comandos SQL em um campo do sistema, fazendo o banco interpretar o texto como parte da consulta.
Por exemplo, se o sistema tiver um campo para pesquisar o título de um livro, uma pessoa poderia tentar colocar um texto malicioso nesse campo. Se o sistema colocar esse texto diretamente no SQL, a consulta pode ser alterada. 





—------------------------------------------------------------------------------------------------------------------------



No arquivo cadastrar os dados do título  autor e ano são recebidos através do formulário e depois colocados diretamente na consulta Sql. Essa forma pode causar problemas de segurança, porque os dados do usuário são inseridos diretamente no comando. 



No arquivo atualizar, os dados recebidos pelo formulário são colocados diretamente na consulta Sql. Isso pode deixar a aplicação vulnerável a Sql Injection, pois os valores recebidos do usuário não estão separados do comando Sql. 






O erro é que o id recebido pelo usuário através de $_GET["id"] é inserido diretamente na consulta Sql. Isso deixa o sistema vulnerável a Sql Injection, pois o usuário pode manipular esse valor antes de ele ser enviado ao banco de dados.

Codigo corrigido - 



? fica no lugar do ID primeiro, e depois o valor do ID é passado para o comando. Por último, a consulta é executada. Isso é mais seguro porque o ID não é colocado diretamente dentro do comando SQL. 


Link do Fork - https://github.com/matheustomczak-dev/crud_livraria.git


















































































