-- Criação da tabelas empregados --

CREATE TABLE public.empregados (
                matricula_id VARCHAR NOT NULL,
                nome VARCHAR(255) NOT NULL,
                telefone VARCHAR(20),
                cpf VARCHAR NOT NULL,
                email VARCHAR(255) NOT NULL,
                CONSTRAINT empregados_pk PRIMARY KEY (matricula_id)
);
COMMENT ON COLUMN public.empregados.matricula_id IS 'matricula_id referente ao id da tabela empregados com a caracteristica varchar é uma primary key e é not null';
COMMENT ON COLUMN public.empregados.nome IS 'coluna nome, referente ao nome dos empregados tem como caracteristica o varchar 255 e not null';
COMMENT ON COLUMN public.empregados.telefone IS 'coluna telefone, referente ao nome dos empregados tem como caracteristica o varchar 20';
COMMENT ON COLUMN public.empregados.cpf IS 'coluna cpf, referente ao nome dos empregados tem como caracteristica o varchar e not null';
COMMENT ON COLUMN public.empregados.email IS 'coluna email, referente ao nome dos empregados tem como caracteristica o varchar 255 e not null';


-- Criação da tabelas aulas --

CREATE TABLE public.aulas (
                curso_id VARCHAR NOT NULL,
                matricula_id VARCHAR NOT NULL,
                cursos VARCHAR,
                duracao VARCHAR,
                CONSTRAINT aulas_pk PRIMARY KEY (curso_id)
);
COMMENT ON COLUMN public.aulas.curso_id IS 'curso_id referente ao id da tabela aulas com a caracteristica varchar e é uma pk e not null';
COMMENT ON COLUMN public.aulas.matricula_id IS 'coluna matricula_id, referente a tabela aulas tem como caracteristica o varchar é fk e not null';
COMMENT ON COLUMN public.aulas.cursos IS 'coluna cursos, referente a tabela aulas e tem como caracteristica o varchar';
COMMENT ON COLUMN public.aulas.duracao IS 'coluna duracao, referente a tabela aulas e tem como caracteristica o varchar ';


-- Criação da tabelas cursos --

CREATE TABLE public.cursos (
                curso_id VARCHAR NOT NULL,
                curso VARCHAR NOT NULL,
                CONSTRAINT cursos_pk PRIMARY KEY (curso_id)
);
COMMENT ON COLUMN public.cursos.curso_id IS 'curso_id referente ao id da tabela aulas com a caracteristica varchar e é uma pk e not null';
COMMENT ON COLUMN public.cursos.curso IS 'coluna cursos, referente a tabela cursos e tem como caracteristica o varchar e not null';


-- Criação da tabelas desempenho --

CREATE TABLE public.desempenho (
                matricula_id VARCHAR NOT NULL,
                curso_id VARCHAR NOT NULL,
                pontos VARCHAR,
                CONSTRAINT desempenho_pk PRIMARY KEY (matricula_id)
);
COMMENT ON COLUMN public.desempenho.matricula_id IS 'matricula_id referente ao id da tabela desempenho com a caracteristica varchar é uma primary key e é not null';
COMMENT ON COLUMN public.desempenho.curso_id IS 'coluna curso_id, referente a tabela desempenho com a caracteristica varchar e é uma fk e not null';
COMMENT ON COLUMN public.desempenho.pontos IS 'coluna pontos, referente a tabela desempenho com a caracteristica varchar ';



-- Criação da tabelas desempenho --

CREATE TABLE public.progresso (
                matricula_id VARCHAR NOT NULL,
                horas NUMERIC,
                paginas VARCHAR,
                atividades VARCHAR,
                CONSTRAINT progresso_pk PRIMARY KEY (matricula_id)
);
COMMENT ON COLUMN public.progresso.matricula_id IS 'matricula_id referente ao id da tabela progresso com a caracteristica varchar é uma pfk e é not null';
COMMENT ON COLUMN public.progresso.horas IS 'coluna horas, referente a tabela progresso com a caracteristica numeric';
COMMENT ON COLUMN public.progresso.paginas IS 'coluna paginas, referente a tabela progresso com a caracteristica varchar ';
COMMENT ON COLUMN public.progresso.atividades IS 'coluna atividades, referente a tabela progresso com a caracteristica varchar ';

                         
                         ----------------------------------------------------------------------
                         -------------------- Criação da FK -----------------------------
                         ----------------------------------------------------------------------
-- FK da tabela aulas --
ALTER TABLE public.aulas 
ADD CONSTRAINT empregados_aulas_fk
FOREIGN KEY (matricula_id)
REFERENCES public.empregados (matricula_id)
ON DELETE NO ACTION
ON UPDATE NO ACTION
NOT DEFERRABLE;

-- FK da tabela desempenho --
ALTER TABLE public.desempenho 
ADD CONSTRAINT empregados_desempenho_fk
FOREIGN KEY (matricula_id)
REFERENCES public.empregados (matricula_id)
ON DELETE NO ACTION
ON UPDATE NO ACTION
NOT DEFERRABLE;

-- FK da tabela desempenho --
ALTER TABLE public.desempenho 
ADD CONSTRAINT aulas_desempenho_fk
FOREIGN KEY (curso_id)
REFERENCES public.aulas (curso_id)
ON DELETE NO ACTION
ON UPDATE NO ACTION
NOT DEFERRABLE;

-- FK da tabela cursos --
ALTER TABLE public.cursos 
ADD CONSTRAINT aulas_cursos_fk
FOREIGN KEY (curso_id)
REFERENCES public.aulas (curso_id)
ON DELETE NO ACTION
ON UPDATE NO ACTION
NOT DEFERRABLE;

-- FK da tabela progresso --
ALTER TABLE public.progresso 
ADD CONSTRAINT desempenho_progresso_fk
FOREIGN KEY (matricula_id)
REFERENCES public.desempenho (matricula_id)
ON DELETE NO ACTION
ON UPDATE NO ACTION
NOT DEFERRABLE;

