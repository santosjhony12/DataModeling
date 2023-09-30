# MODELAGEM DE DADOS - INICIANDO ... 
<h5>Data: 18/08/2023</h5>

- 1º Passo: Entender o problema.
- 2º Passo: Conceituar - Modelo conceitual: Modelo Entidade-Relacionamento (MER)

<h4>Entidade: </h4>

> Conceito: Qualquer coisa que você tem dados à armazenar.<br>
> Tudo que tiver em plural é uma entidade.<br>
> No conceitual tenho que deixar um identificador único - NELE pode ser o nome - Não colocar no ID em tudo no CONCEITUAL <br>
> Quando for combinação de dois atributos únicos pode colocar o preenchimento<br>

<h5>Data: 24/08/2023</h5>

<h4>Relacionamento: </h4>

>O Relacionamento é o que conecta as entidades.<br>
>Não é necessário que todas as entidades estejam conectadas.

<h4>Cardinalidade: </h4>

> ‼️ É INVERTIDO (o lado da cardinalidade)‼️<br>
> Utilizar apenas n(muitos) e 1<br>
> Máximo: 1 e n - Quantos?<br>
> Mínimo: 0 - opcional / 1 - obrigatório - É obrigatório?<br>
> (minimo, maximo) / (0,1)<br>
> O obrigatório não é muito bom utilizar em massa<br>
> São chamados de restrições<br>

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/e300f448-3ac5-45cb-b9df-7d4f32ed4ede)


<h4>Modelagem de Torneio</h4>

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/d7027c35-552c-40aa-9d52-912ab73257e4)



<h4>Anotações: </h4>

- Product Backlog and Users Stores - As users stores da segunda Sprint devem estar detalhadas - DoR DoD)
- As primeiras não podem ser epicas - pois vamos trabalhar na primeira sprint

> Como [tipo usuario] <br> desejo [alguma coisa] <br> para [finalidade]

- Definition of Right (Pronto pra desenvolver) - Team
- Definition of Done (Exe. Como rodar, oq instalar, codigo) - Quem é responsável? PO
- Na 1º Sprint deve ter um projeto Java no git
- A partir da segunda sprint, todos devem commitar
- Modelo de dados inicial (2 ou 3 entidades) - 1º Sprint
- NUNCA COMEÇAR COM LOGIN, SEMPRE PELO OQ É MAIS PRIORITÁRIO AO CLIENTES


<h4>Aula 14/09</h4>

- AutoRelacionamento: Entidade sendo relacionado consigo mesmo.

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/bf119cf2-fb22-46a8-8a7a-5bc5a7b45a0d)

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/4f08fad4-3327-4223-b766-347830ad800b)


- Entidade Fraca: Critério Temporal - O traço mais grosso pega todos os identificadores

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/962b339a-8185-4248-add8-5631681d291f)


- Generalização

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/3e2ee262-b328-42a7-b4ce-bd05722d7ce0)




<h5>Não precisa de cardinalidade</h5>

![image](https://github.com/santosjhony12/ModelagemDados/assets/123211025/ac50944c-cd54-4bc6-8a74-dfd3ae8cee5f)


## SQL - Structured Query Language 

<h3>28/09/2023</h3>

- Primeiros códigos no MySQL

- SCHEMA e DATABASE no MySql são iguais, não causa problema em nada.

<h2>DDL - Data Definition Language</h2>

```
CREATE SCHEMA fatec;
USE fatec;

CREATE TABLE curso(
  id BIGINT AUTO_INCREMENT,
  nome VARCHAR(50) NOT NULL UNIQUE,
  PRIMARY KEY(id)
);

CREATE TABLE aluno(
  ra BIGINT AUTO_INCREMENT,
  nome VARCHAR(255) NOT NULL,
  data_matricula DATE,
  id_curso BIGINT NOT NULL,
  PRIMARY KEY (ra), -- usada pra compostas
  FOREIGN KEY fk_aluno_curso (id_curso) REFERENCES curso (id)
);

```
<h2>DML - Data Manipulation Language</h2>

```
-- INSERIR ALGUMA COISA
INSERT INTO tabela(campos) VALUES(valores);

-- ATUALIZAR ALGUMA COISA
UPDATE tabela
SET campo = valor WHERE campo = valor;

-- DELETAR ALGUMA COISA
DELETE FROM tabela WHERE campo = valor;
```

<h2>DQL - Data Query Language</h2>

```
-- SELECIONAR A TABELA COMPLETA
SELECT * FROM tabela;

-- SELECIONAR ALGUM CAMPO
SELECT campo FROM tabela;

-- SELECIONAR COM CODIÇÃO
SELECT * FROM tabela WHERE campo = valor;
SELECT * FROM tabela LIKE campo = '%algumacoisa%';
SELECT data FROM calendario WHERE data >= 2022-02-12;

-- JUNTANDO TABELAS
SELECT tabela1.campo, tabela2.campo FROM tabela1
INNER JOIN tabela2;

-- APELIDANDO OS CAMPOS
SELECT campo AS apelido FROM tabela;
```
