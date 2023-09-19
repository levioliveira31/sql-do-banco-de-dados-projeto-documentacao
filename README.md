# sql-do-banco-de-dados-projeto-documentacao
sql do banco de dados referente a um software para verificar a validade de documentos

create database projeto_documentacao;

use projeto_documentacao;

CREATE TABLE tbl_documentacao(
  id_doc int(15) auto_increment primary key,
  nm_doc char(40),
  tipo_doc char(10),
  emissao date,
  vencimento date
);

CREATE TABLE tbl_cliente(
  id_cliente int(15) auto_increment primary key,
  email char(40),
  cpf int(15),
  endereco char(70),
  nome char(60),
  dt_nasc char(12),
  id_doc int(15),
  foreign key(id_doc) references tbl_documentacao(id_doc)
);

CREATE TABLE tbl_telefone(
  id_cliente int(15),
  id_fone int(15),
  telefone char(8),
  foreign key(id_cliente) references tbl_cliente(id_cliente)
);
