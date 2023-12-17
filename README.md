# SQL-material-de-apoio

# O que é o MYSQL?
● SGBD - Sistema Gerenciador de Banco de Dados relacional e gratuito.

● SQL - Structured Query Language ou Linguagem de Consulta Estruturada: é uma linguagem de programação padronizada usada para gerenciar bancos de dados relacionais e executar várias operações nas informações que eles contêm.

● Criado inicialmente na década de 1970, o SQL é comumente usado não apenas por administradores de banco de dados, mas também por desenvolvedores que escrevem scripts de integração de dados e por analistas de dados que desejam configurar e executar consultas analíticas;

● O sql é adotado como uma linguagem padrão nos principais bancos relacionais existentes hoje no mercado

![tipos de bancos de dados](https://github.com/vitorgesteira/SQL-material-de-apoio/assets/54457455/5f33e969-9a31-4131-96d8-c49378f88f5b)


● Definir - manipular - controlar - transacionar - recuperar dados

● Existem divisões para cada conceito no SQL e os mais comuns são DML, DDL e DCL.


# São 5 Divisões

● DDL - Data Definition Language - Linguagem de definição de dados

● DML - Data Manipulation Language - Linguagem de manipulação de dados

● DCL - Data Control Language - Linguagem de Controle de Dados

● DTL - Data Transaction Language - Linguagem de Transação de Dados

● DQL - Data Query Language - Linguagem de consulta de dados

# DDL
● A DDL (Data Definition Language) engloba os comandos de definição do banco de dados. Interagem com os objetos do banco. E alguns deles são:

    ○ CREATE - o comando Create cria objetos;
    ○ DROP - o comando Drop exclui objetos do banco de dados;
    ○ ALTER - o ALTER altera objetos já existentes, seja modificando, excluindo ou adicionando;
    ○ TRUNCATE - exclui todo o conteúdo de uma tabela e redefine sua identidade para o valor inicial.

# DML
● A DML (Data Manipulation Language) corresponde aos comandos de manipulação dos dados. E são eles:

    ○ SELECT - o Select recupera dados de determinado lugar;
    ○ INSERT - essa instrução insere dados a uma ou mais tabelas;
    ○ UPDATE - atualiza os dados existentes em uma ou mais tabelas;
    ○ DELETE - exclui os registros de uma tabela ou mais. Quando não acompanhado de uma cláusula, todas as linhas são removidas.

# Comandos SGBD
● Alguns comandos de gerenciamento básico do SGBD são importantes de serem aprendidos. Os principais são:

    ○ SHOW DATABASES - mostra todos os bancos de dados do MySQL;
    ○ SHOW TABLES - mostrar todas as tabelas de um banco de dados;
    ○ USE DATABASE_NAME - se conecta a um banco de dados;
    ○ DESCRIBE TABLE_NAME - mostra os detalhes de uma tabela.

# Modelagem de um Banco Relacional
# Exemplo Geral

● O Modelo entidade relacionamento proposto por Peter P. Chen pode ser melhor compreendido por uma teoria chamada de A lei do Mundo, teoria essa, que conceitua que o mundo está cheio de coisas que possuem características próprias e que se relacionam entre si. Sua análise da teoria pode ser dividida em três partes:

    ○ O mundo está cheio de coisas: tudo que possa ser caracterizado, conceituado, real ou imaginário, no nosso Universo (Mundo)

    ○ Que possuem características próprias: características comuns percebidas entre as coisas de modo que haja a possibilidade de enquadramento dessas coisas em conjuntos particulares.

    ○ E que se relacionam entre si: são as relações entre as coisas.

# Entidades

● É a representação genérica de um componente do mundo real, sobre o qual desejamos armazenar informações;

● Entidade são coisas significativas sobre a qual a organização deseja guardar, ou seja, (coletar, manter e etc) dados podendo ser algo tangível ou intangível;

● Vários autores defendem formas de identificar e classificar as entidades, onde suas tipificações mais comuns são:

    ○ Coisas tangíveis;
    ○ Funções;
    ○ Eventos ou ocorrências.

# Atributos

● Atributo é tudo o que se pode relacionar como próprio da entidade (propriedade) que de alguma maneira a qualifique e a distinga de outras, estes podem ser classificados e identificados como:  

    ○ Atributos Descritivos: atributo que seja capaz de demonstrar, ou representar, características formadoras. Ex: Data de nascimento, idade, sexo;

    ○ Atributos Nominativos: atributo que além de cumprirem a função de descritivos, também servem como definidores de nomes ou rótulos. Ex: código do..., matrícula, número...

    ○ Atributos Referenciais: atributo que não pertencem propriamente a entidade onde estão, mas fazem algum tipo de referência dessa entidade com outra entidade.

# Relacionamento
● Relacionamento é a relação existente entre entidades, isto é a ligação lógica entre duas entidades que representa uma regra ou restrição de negócio;

● Podem ser estabelecidos mais de um relacionamento entre entidades, de acordo com a regra de negócio a ser representada onde cada entidade pode participar de vários relacionamentos.

● Os relacionamentos possuem características que os tipificam:
    
    ○ Cardinalidade: indica a quantidade de ocorrências de determinado relacionamento;

    ○ Opcionalidade: Analisa os relacionamentos pelo lado da obrigatoriedade das ocorrências.

# DDL - Data Definition Language

# Criando o Banco de Dados:
● Após se conectar ao servidor MySQL, é necessário criar o seu Banco de Dados, para isso, utilize o comando:

    CREATE DATABASE database-name;

● Com o seu banco de dados criado, conecte-se a ele por meio do comando:
    
    USE database-name

# Apagando database:
● Para apagar um banco de dados, utilize o comando abaixo:

    DROP DATABASE database-name;

# O que são Tabelas?

● Tabelas são objetos de banco de dados que contêm todos os dados em um banco de dados;

● Nas tabelas, os dados são organizados de maneira lógica em um formato de linha-e-coluna semelhante ao de uma planilha;

● Cada linha representa um registro exclusivo e cada coluna representa um campo no registro;

● Por exemplo, uma tabela que contém dados de funcionários de uma empresa pode conter uma linha para cada funcionário e colunas representando as informações sobre o funcionário, como número, nome, endereço, cargo e número do telefone residencial do funcionário.

# Criar e apagar tabela:
    CREATE TABLE nome-tabela (
        campo1 TIPO CONSTRAINT,
        campo2 TIPO CONSTRAINT
    );

### ex:
    CREATE TABLE tb_cursos(
        id_curso int not null,
        imagem_curso varchar(100) not null,
        nome_curso char(50) not null,
        resumo text null,
        data_cadastro datetime not null,
        ativo boolean default true,
        investimento float(8,2) default 0
    );

    CREATE TABLE tb_descricoes_tecnicas(
        id_descricao_tecnica INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        id_produto INT NOT NULL,
        descricao_tecnica TEXT NOT NULL,
        FOREIGN KEY(id_produto) REFERENCES tb_produtos(id_produto)
    )

# Tipos de dados:

● Campos de texto:

    ○ Text - tamanho variavel que armazena uma grande quantidade de caracteres
    ○ VARCHAR(M) - String de tamanho variável, até 65535 caracteres
    ○ CHAR(M) - String que ocupa tamanho fixo entre 0 e 255 caracteres
    ○ MEDIUMTEXT - Permite armazenar até 16.777.215 caracteres
    ○ LONGTEXT - Permite armazenar até 4.294.967.295 caracteres

● Campos numericos:

    ○ INT - valores numericos inteiros
    ○ FLOAT(M,D) - valores numericos fracionados
    ○ DECIMAL(M,D) - Ponto decimal com M dígitos no total (precisão) e D casas decimais (escala)

● Campos de data e hora:

    ○ DATE - Uma data de 01/01/1000 a 31/12/9999, no formato YYYY-MM-DD
    ○ TIME - Hora apenas, no formato HH:MM:SS
    ○ DATETIME - Uma combinação de data e hora de 01/01/1000 00:00:00 a 31/12/9999 23:59:59, no formato YYYY-MM-DD HH:MM:SS
    
● Campos Booleano: 

    ○ BOOL / BOOLEAN - Valores binários 0 / 1
    ○ BLOB / MEDIUMBLOB/ TINYBLOB - Campo com tamanho máximo de 65535 caracteres binários
        

# Constraints (Restrições)

● As restrições SQL são usadas para especificar regras para os dados em uma tabela. As restrições são usadas para limitar o tipo de dados que podem entrar em uma tabela.

    ○ NOT NULL - Garante que uma coluna não pode ter um valor NULL
    ○ UNIQUE - Garante que todos os valores em uma coluna sejam diferentes
    ○ PRIMARY KEY - Uma combinação de NOT NULL e UNIQUE. Identifica exclusivamente cada linha em uma tabela
    ○ FOREIGN KEY - Identifica exclusivamente uma linha/registro em outra tabela
    ○ DEFAULT ‘VALUE’ - Define um valor padrão para uma coluna quando nenhum valor é especificado
    ○ CHECK (CONDITION) - Garante que todos os valores em uma coluna satisfaçam uma condição específica
    ○ INDEX - Usado para criar e recuperar dados do banco de dados muito rapidamente



# Alterando uma Coluna (ALTER);
● Para alterar uma coluna no banco de dados, utilize o comando abaixo:

    ALTER TABLE nome-tabela
    ADD COLUMN campo TIPO CONSTRAINT;

    ALTER TABLE nome-tabela
    DROP COLUMN campo;

    ALTER TABLE nome-tabela
    MODIFY COLUMN campo TIPO CONSTRAINT;

# Apagando uma Tabela
● Para apagar uma tabela, utilize o comando abaixo:

    DROP TABLE nome-tabela;

# DML - Data Manipulation Language

# Inserindo Registros
● Após criar a tabela, agora é necessário inserir dados. Para inserir um registro,
utilize o comando abaixo:

    INSERT INTO nome-tabela (campo1, campo2)
    VALUES (valor1, valor2);

# Inserindo Múltiplos Registros
● Para inserir múltiplos registros, utilize o comando abaixo:

    INSERT INTO nome-tabela (campo1, campo2)
    VALUES (valor1, valor2), (valor1, valor2);

# Buscando Registros
● Para buscar registros, utilize o comando abaixo:

    SELECT campo1, campo2
    FROM nome-tabela;

● Para buscar todos os campos, de todos os registros:

    SELECT * 
    FROM nome-tabela;

# Cláusula Where
● A cláusula Where é utilizada para fazer condições, seja para busca, atualização ou remoção;

● Essa cláusula permite criar restrições que limitam quais dados irão sofrer alterações ou irão ser buscados;

● Para utilizá-lo, siga a sintaxe abaixo:

    SELECT nome 
    FROM pessoa 
    WHERE nome = ‘John Doe’;

# IN
● O operador IN permite especificar vários valores em uma cláusula WHERE.

● O operador IN é um atalho para várias condições OR;

    SELECT campo 
    FROM nome-tabela 
    WHERE campo IN (value1, value2, ...);

# Between
● O operador BETWEEN seleciona valores dentro de um determinado intervalo.

● Os valores podem ser números, texto ou datas.

● O operador BETWEEN é inclusivo: os valores inicial e final são incluídos.

    SELECT campo 
    FROM nome-tabela 
    WHERE campo BETWEEN valor1 AND valor2;

# Order By
● O ORDER BY é usado para classificar o conjunto de resultados em ordem crescente ASC ou decrescente DESC;

● Por padrão, os registros são ordenados em ordem crescente. Para classificar os registros em ordem decrescente, use a palavra- DESC.

    SELECT campo 
    FROM nome-tabela 
    ORDER BY campo1, campo2, ... ASC | DESC

# Wildcards
● Wildcards (Cartões Coringa) são utilizados na consultas SQL junto com o operador LIKE para achar dados de maneira mais personalizada.

● Com esses operadores é possível buscar dados que contenham, começam ou terminam com certos valores.

● Os Wildcards são:

    ○ % - significa vários caracteres de qualquer coisa.

    ○ _ - significa um carácter de qualquer coisa.

## Wildcards - Exemplos
● Utilizando o wildcard %:

    SELECT campo 
    FROM nome-tabela 
    WHERE campo LIKE ‘%filtro%’

● Utilizando o wildcard _:

    SELECT campo 
    FROM nome-tabela 
    WHERE campo LIKE ‘_filtro’

# Atualizando Registros
● Para atualizar registros, basta seguir o comando abaixo:

    UPDATE nome-tabela 
    SET campo = novo-valor 
    WHERE campo = valor-filtro;

● Lembre-se de sempre usar o WHERE, caso contrário, todos os registros serão atualizados.

# Deletando Registros
● Para deletar registros, basta seguir o comando abaixo:

    DELETE FROM nome-tabela
    WHERE campo = valor-filtro;

● Lembre-se de sempre usar o WHERE, caso contrário, todos os registros serão apagados. O comando abaixo apaga todos os registros:

    DELETE FROM nome-tabela;

# Relacionamentos com SQL

# Relacionamento entre tabelas

● Existem três níveis de relacionamento entre tabelas:

    ○ um-para-muitos ( 1 : N )
    ○ um-para-um ( 1 : 1 )
    ○ muitos-para-muitos ( N : N)

● Com o tempo você se acostuma e identifica em qual desses níveis a sua regra de negócio se encaixa.

# Primary Key

● Chave primária é uma constraint utilizada nos bancos de dados relacionais;

● Chave primária (Primary Key) são utilizadas nos bancos de dados relacionais para definir que aquela entidade (row) é única;

● O seu uso está relacionado para definir unicidade as entidades, evitando assim, o problema de repetição e redundância entre as relações e os registros;

● Primary key são definidas em uma coluna na tabela, podendo ser definidas mais de uma chave primária;

# Primary Key - Tipos

● Surrogate Key - chave sintética. Uma chave primária que não possui sentido para entidades, servindo apenas como identificador único.

● Natural Key - chave natural. Uma chave primária que possui sentido para entidade. Um exemplo clássico é o CPF.

## Características

● Única - toda chave primária é única e não se repete entre as entidades.

● Não nula - a chave primária não pode ser vazia ou nula.

● Não muda - é possível mudar chaves primárias, mas é um processo muito dificultoso, portanto, em via de regra, a chave primária não muda.

# Primary Key - Sintaxe

● As duas formas possíveis de criar chaves primárias estão abaixo:

    CREATE TABLE Person (
        ID INT NOT NULL,
        PRIMARY KEY (ID)
    );

    CREATE TABLE Person (
        ID INT PRIMARY KEY
    );

# Foreign Key

● Chave estrangeira é uma coluna ou grupo de colunas em uma tabela de banco de dados relacional que fornece um link entre dados em duas tabelas.

● Ele atua como uma referência cruzada entre tabelas porque faz referência à chave primária de outra tabela, estabelecendo assim um link entre elas.

● A maioria das tabelas em um sistema de banco de dados relacional adere ao conceito de chave estrangeira.

● O conceito de integridade referencial é derivado da teoria da chave estrangeira.

● As chaves estrangeiras e sua implementação são mais complexas que as chaves primárias.

# Foreign Key - Sintaxe

● Para criar uma chave estrangeira, utilize o comando abaixo:
    CREATE TABLE Person (
        nome VARCHAR(255),
        trabalho_id INT
        FOREIGN KEY trabalho_id REFERENCES Trabalho(id)

# Relacionamento 1 : N

● Vamos supor a relação entre as entidades livro e autor, nesse caso, um livro só pertence a um autor, mas os autores podem ter vários livros;

● Vamos criar o Banco de Dados chamado modelo relacional com duas tabelas: autores e livros e cada tabela com suas colunas;

● Abaixo, o código sql para criar o banco de dados, as tabelas, as colunas e a inserção dos dados:

DDL:

    -- Cria o banco de dados Modelo Relacional --
    CREATE DATABASE IF NOT EXISTS modelo_relacional;
    USE modelo_relacional;

    -- Cria a tabela Autores --
    CREATE TABLE IF NOT EXISTS autores (
	    id INT NOT NULL AUTO_INCREMENT,
	    nome VARCHAR(50) NOT NULL,
	    id_livro INT NOT NULL,
	    PRIMARY KEY (id),
	    FOREIGN KEY id_livro REFERENCES livros(id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=latin1;

    -- Cria a tabela Livros --
    CREATE TABLE IF NOT EXISTS livros (
        id INT NOT NULL AUTO_INCREMENT,
        nome VARCHAR(50) NOT NULL,
        PRIMARY KEY (id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=latin1;

DML:

    /*
    - Insira os dados nessa ordem: primeiro os livros depois os autores
    */
    -- Insere os dados na tabela Livros
    INSERT INTO livros (id, nome) VALUES (1, 'A Culpa É das Estrelas');
    INSERT INTO livros (id, nome) VALUES (2, 'Quem É Você, Alasca?');
    INSERT INTO livros (id, nome) VALUES (3, 'O corvo');
    INSERT INTO livros (id, nome) VALUES (4, 'O gato preto');
    INSERT INTO livros (id, nome) VALUES (5, 'Harry Potter e a pedra filosofal');
    INSERT INTO livros (id, nome) VALUES (6, 'Harry Potter e o prisioneiro de Azkaban');
    INSERT INTO livros (id, nome) VALUES (7, 'A Menina que Roubava Livros');

    -- Insere os dados na tabela Autores
    INSERT INTO autores (id, nome, id_livro) VALUES (1, 'John Green', 1);
    INSERT INTO autores (id, nome, id_livro) VALUES (2, 'John Green', 2);
    INSERT INTO autores (id, nome, id_livro) VALUES (3, 'Edgar Allan Poe', 3);
    INSERT INTO autores (id, nome, id_livro) VALUES (4, 'Edgar Allan Poe', 4);
    INSERT INTO autores (id, nome, id_livro) VALUES (5, 'J.K. Rowling', 5);
    INSERT INTO autores (id, nome, id_livro) VALUES (6, 'J.K. Rowling', 6);
    INSERT INTO autores (id, nome, id_livro) VALUES (7, 'Markus Zusak', 7);

# Relacionamento 1 : 1

● Vamos supor a relação entre as entidades Cliente e Endereço, nesse caso, um cliente tem um endereço e um endereço pertence a apenas um cliente;

● Nesse tipo de relacionamento, vamos ter duas tabelas que são: tabela endereços e tabela clientes;

● Abaixo, o código sql para criar o banco de dados, as tabelas e as colunas e a inserção dos dados:

DDL:

    USE modelo_relacional;

    -- Cria a tabela Endereços --
    CREATE TABLE IF NOT EXISTS endereços (
        id INT NOT NULL AUTO_INCREMENT,
        rua VARCHAR(60) NOT NULL,
        bairro VARCHAR(60) NOT NULL,
        numero INT NOT NULL,
        cidade VARCHAR(60) NOT NULL,
        id_cliente INT NOT NULL,
        PRIMARY KEY (id),
    FOREIGN KEY id_cliente REREFERENCES clientes(id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=LATIN1;

    -- Cria a tabela Clientes
    CREATE TABLE IF NOT EXISTS clientes (
        id INT NOT NULL AUTO_INCREMENT,
        nome VARCHAR(60) NOT NULL,
        celular INT NOT NULL,
        email VARCHAR(70) NOT NULL,
        PRIMARY KEY (id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=LATIN1;

DML:

    -- Insere os dados na tabela clientes
    INSERT INTO clientes (id, nome, celular, email) VALUES
    (1, 'John Green', 992345132, 'john@gmail.com'),
    (2, 'Edgar Allan Poe', 993412098, 'edgar@gmail.com'),
    (3, 'J.K. Rowling', 993186509, 'jkrow@gmail.com'),
    (4, 'Markus Zusak', 84512983, 'markus@gmail.com');

    -- Insere os dados na tabela endereços
    INSERT INTO endereços (id, rua, bairro, numero, cidade, id_cliente) VALUES
    (1, 'Leonardo da Vince', 'Jardim da saúde', 433, 'Cacoal', 3),
    (2, 'Rodrigo Salvatori', 'Teixeirão', 176, 'Cacoal', 4),
    (3, 'Cambé', 'Valparaiso', 3410, 'Ji-Paraná', 2),
    (4, 'Olinda', 'JK', 6309, 'Ji-Paraná', 1);

# Relacionamento N : N

● Vamos supor a relação entre as entidades Cliente e Produto, nesse caso, um cliente pode comprar vários produtos, assim como um produto pode ser comprado por varios clientes;

● Nesse tipo de relacionamento, vamos ter três tabelas que são: tabela clientes, tabela produtos e tabela compra, onde na terceira tabela é para inserir informações como qual produto foi comprado e por qual cliente;

● Abaixo, o código sql para criar o banco de dados, as tabelas e as colunas e a inserção dos dados:

DDL:

    -- Cria a tabela Cliente --
    CREATE TABLE IF NOT EXISTS clientes (
        id INT NOT NULL AUTO_INCREMENT,
        nome VARCHAR(50) NOT NULL,
        PRIMARY KEY (id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=LATIN1;

    -- Cria a tabela Produtos --
    CREATE TABLE IF NOT EXISTS produtos (
        id INT NOT NULL AUTO_INCREMENT,
        nome VARCHAR(50) NOT NULL,
        PRIMARY KEY (id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=LATIN1;

    -- Cria a tabela Compras --
    CREATE TABLE IF NOT EXISTS compras (
        id INT NOT NULL AUTO_INCREMENT,
        id_cliente INT NOT NULL,
        id_produto INT NOT NULL,
        PRIMARY KEY (id),
    FOREIGN KEY id_cliente REFERENCES clientes(id),
    FOREIGN KEY id_produto REFERENCES produtos(id)
    ) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=latin1;

DML:

    -- Insere os dados na tabela Cliente
    INSERT INTO cliente (id, nome) VALUES (1, 'José da Silva');
    INSERT INTO cliente (id, nome) VALUES (2, 'Laura Carvalho');
    INSERT INTO cliente (id, nome) VALUES (3, 'Natan Gloss');
    INSERT INTO cliente (id, nome) VALUES (4, 'Vinicius Sales');
    INSERT INTO cliente (id, nome) VALUES (5, 'Rogerio Valin');
    INSERT INTO cliente (id, nome) VALUES (6, 'Bianca Albuquerque');

    -- Insere os dados na tabela Produtos
    INSERT INTO produtos (id, nome) VALUES (1, 'Caneca Coffee');
    INSERT INTO produtos (id, nome) VALUES (2, 'Borracha Redbor');
    INSERT INTO produtos (id, nome) VALUES (3, 'Lápis Cis Nataraj');
    INSERT INTO produtos (id, nome) VALUES (4, 'Caderno Tilibra 96 folhas');
    INSERT INTO produtos (id, nome) VALUES (5, 'Caneta Bic preta');
    INSERT INTO produtos (id, nome) VALUES (6, 'Régua New Line 30cm');
    INSERT INTO produtos (id, nome) VALUES (7, 'Cola Jocar');

    -- Insere os dados na tabela Compras
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (1, 1, 1);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (2, 1, 2);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (3, 2, 1);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (4, 3, 4);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (5, 3, 5);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (6, 4, 3);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (7, 4, 2);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (8, 5, 7);
    INSERT INTO compras (id, id_cliente, id_produto) VALUES (9, 6, 1);

# Junção de tabelas com JOIN

● O JOIN é uma cláusula usada para combinar linhas de duas ou mais tabelas, com base em uma coluna relacionada entre elas;

● Os joins são definidos em quatro formas:

    ○ INNER JOIN;
    ○ LEFT JOIN;
    ○ RIGHT JOIN;
    ○ CROSS JOIN.

● O join pode ser imaginado com a intercessão entre duas tabelas, onde para haver tal intercessão é necessário existir uma relação entre as tabelas com a passagem de foreign keys.

# INNER JOIN

● INNER JOIN seleciona registros que possuem valores correspondentes em ambas as tabelas;

● Com isso, serão retornados apenas os registros que existem na intercessão, entre chave estrangeira e chave primária.

    SELECT * FROM TABELA_1 t1
    INNER JOIN TABELA_2 t2
    ON t1.chave_estrangeira = t2.chave_primaria

# LEFT JOIN

● LEFT JOIN seleciona registros que possuem valores correspondentes em ambas as tabelas e caso, existam registros que não correspondam em ambas tabelas, na tabela 1, eles serão selecionados mesmo assim;

● Com isso, serão retornados apenas os registros que existem na intercessão e no lado esquerdo da intercessão, entre chave estrangeira e chave primária.

    SELECT * FROM TABELA_1 t1
    LEFT JOIN TABELA_2 t2
    ON t1.chave_estrangeira = t2.chave_primaria

# RIGHT JOIN

● RIGHT JOIN seleciona registros que possuem valores correspondentes em ambas as tabelas e caso, existam registros que não correspondam em ambas tabela na tabela 2, eles serão selecionados mesmo assim;

● Com isso, serão retornados apenas os registros que existem na intercessão e no lado direito da intercessão, entre chave estrangeira e chave primária.

    SELECT * FROM TABELA_1 t1
    RIGHT JOIN TABELA_2 t2
    ON t1.chave_estrangeira = t2.chave_primaria

# CROSS JOIN

● CROSS JOIN seleciona registros que possuem valores correspondentes em ambas as tabelas e caso, existam registros que não correspondam em ambas tabelas, na tabela 1 e 2, eles serão selecionados mesmo assim;

● Com isso, serão retornados todos os registros que existem na intercessão e no lado esquerdo e direito da intercessão, entre chave estrangeira e chave primária.

    SELECT * FROM TABELA_1 t1
    CROSS JOIN TABELA_2 t2
    ON t1.chave_estrangeira = t2.chave_primaria

