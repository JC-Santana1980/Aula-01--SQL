Primeira aula de MySQL Workbench.


-- Cria o banco de Dados Loja
CREATE DATABASE loja;

--Mostra todos os bancos do servidor
SHOW DATABASES;

-- Escolhe o banco que vamos usar
USE loja;

CREATE TABLE cliente(
id INT AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(100) NOT NULL,
email varchar(100) NOT NULL UNIQUE
);cliente

CREATE TABLE produto(
id INT AUTO_INCREMENT PRIMARY KEY,
NOME VARCHAR(100) NOT NULL,
preco DECIMAL(5,2) NOT NULL
 );

CREATE TABLE pedido(
id INT AUTO_INCREMENT PRIMARY KEY,
data_pedido date NOT NULL,
cliente_id int NOT NULL,
produto_id int NOT NULL,
FOREIGN KEY (cliente_id) REFERENCES cliente(id),
FOREIGN KEY (produto_id) REFERENCES produto(id)
 ); 
 
 
 --Acrescenta colunas em tabelas existentes.
 
 ALTER TABLE cliente ADD telefone VARCHAR (20);
 
 -- Alterar o nome de uma coluna que esta incorreta
 
 ALTER TABLE cliente CHANGE telefone Celular VARCHAR (20);
 
 ALTER TABLE cliente MODIFY celular VARCHAR (20) NOT NULL;
 
 SELECT * FROM cliente  join 
 
SELECT * FROM pedido p 
INNER JOIN cliente c ON p.cliente_id = c.id
INNER JOIN produto pr ON p.produto_id = pr.id;

-- Apaga uma tabela
--DROP TABLE pedido;
--DROP DATABASE loja 
 
