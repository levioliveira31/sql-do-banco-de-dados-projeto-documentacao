# sql-do-banco-de-dados-projeto-documentacao
sql do banco de dados referente a um software para verificar a validade de documentos

create database projeto_de_documentacao;

use projeto_de_documentacao;

CREATE TABLE tbl_documentacao(
  id_doc int(15) auto_increment primary key,
  nm_doc char(40) not null,
  tipo_doc char(10)not null,
  emissao date not null,
  vencimento date not null
);

CREATE TABLE tbl_cliente(
  id_cliente int(15) not null auto_increment primary key,
  email char(40) not null,
  cpf int(15) not null,
  endereco char(70) not null,
  nome char(60) not null,
  dt_nasc char(12) not null,
  id_doc int(15) not null,
  foreign key(id_doc) references tbl_documentacao(id_doc)
);

CREATE TABLE tbl_telefone(
  id_fone int(15) not null AUTO_INCREMENT primary key,
  id_cliente int(15) not null,
  telefone char(8) not null,
  foreign key(id_cliente) references tbl_cliente(id_cliente)
);
  id_cliente int(15),
  id_fone int(15),
  telefone char(8),
  foreign key(id_cliente) references tbl_cliente(id_cliente)
);
