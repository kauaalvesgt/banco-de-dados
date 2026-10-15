# banco-de-dados
-- CRIANDO A TABEÇA DE EDITORAS
CREATE TABLE editoras(
	id_editora SERIAL PRIMARY KEY, 
	nome VARCHAR(60) NOT NULL UNIQUE
)

CREATE TABLE autor(
	id_autores SERIAL PRIMARY KEY,
	nome VARCHAR(60) NOT NULL UNIQUE
)

CREATE TABLE livros(
	id_livros SERIAL NOT NULL,
	nome_livro VARCHAR(100) NOT NULL ,
	ano INTEGER,
	id_editora INTEGER NOT NULL,
	Id_autores INTEGER NOT NULL,
		CONSTRAINT pk_livros
			PRIMARY KEY(id_livros),
		CONSTRAINT dominio_ano
			CHECK(ano BETWEEN 1950 and 2026),
		CONSTRAINT fk_livros_editoras
			FOREIGN KEY(id_editora) REFERENCES editoras(id_editora), 
		CONSTRAINT fk_livros_autor
			FOREIGN KEY(id_autores) REFERENCES autor(id_autores)	






)
