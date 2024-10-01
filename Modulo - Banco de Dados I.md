-- Criação da tabela endereco
CREATE TABLE endereco (
    codigo_endereco INT PRIMARY KEY,
	cod_postal INT,
	numero INT,
    rua VARCHAR(150),
    bairro VARCHAR(100),
    cidade VARCHAR(100),
    estado VARCHAR(25)
);

-- Criação da tabela clientes
CREATE TABLE clientes (
    codigo_cliente INT PRIMARY KEY,
    nome_cliente VARCHAR(50),
    sobrenome_cliente VARCHAR(100),
    codigo_tipo_cliente INT,
    tipo_cliente VARCHAR(50),
    cod_endereco INT,
    CONSTRAINT fk_cod_endereco
        FOREIGN KEY (cod_endereco)
        REFERENCES endereco (codigo_endereco)
);

-- Criação da tabela produtos
CREATE TABLE produtos (
    codigo_produto INT PRIMARY KEY,
    tipo_produto VARCHAR(50) UNIQUE,
    codigo_tipo_produto INT,
    nome_produto VARCHAR(50),
    descricao_produto VARCHAR(100),
    nome_diretor VARCHAR(50),
    email_diretor VARCHAR(50),
    codigo_diretor INT
);

-- Criação da tabela transacoes
CREATE TABLE transacoes (
    id_transacao INT PRIMARY KEY,
    id_cliente INT,
    id_produto INT,
    CONSTRAINT fk_id_cliente
        FOREIGN KEY (id_cliente)
        REFERENCES clientes (codigo_cliente),
    CONSTRAINT fk_id_produto
        FOREIGN KEY (id_produto)
        REFERENCES produtos (codigo_produto)
);

-- Criação da tabela tel_cliente
CREATE TABLE tel_cliente (
    id_tel_cliente INT,
    telefone_cliente VARCHAR(14) UNIQUE,
    CONSTRAINT fk_tel_cliente
        FOREIGN KEY (id_tel_cliente)
        REFERENCES clientes (codigo_cliente)
);

-- Inserção de dados fictícios na tabela endereco
INSERT INTO endereco (codigo_endereco, cod_postal, numero, rua, bairro, cidade, estado)
VALUES
(1, 74429322, 5805, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(2, 19924269, 4676, 'Rua do Comércio', 'Jardim América', 'São Paulo', 'SP'),
(3, 74160659, 8277, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(4, 11867871, 7284, 'Rua das Flores', 'Centro', 'São Paulo', 'SP'),
(5, 30197241, 3338, 'Avenida Afonso Pena', 'Savassi', 'Belo Horizonte', 'MG'),
(6, 83328178, 1645, 'Rua XV de Novembro', 'Centro', 'Curitiba', 'PR'),
(7, 74346495, 2304, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(8, 22798934, 7622, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ'),
(9, 41226950, 6466, 'Rua Marques de Leão', 'Barra', 'Salvador', 'BA'),
(10, 82073421, 2730, 'Rua XV de Novembro', 'Centro', 'Curitiba', 'PR'),
(11, 29720272, 609, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(12, 41286684, 2726, 'Rua Marques de Leão', 'Barra', 'Salvador', 'BA'),
(13, 29615928, 5968, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(14, 16593154, 7688, 'Rua do Comércio', 'Jardim América', 'São Paulo', 'SP'),
(15, 22787968, 993, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ'),
(16, 74789656, 4018, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(17, 92970802, 4500, 'Avenida Ipiranga', 'Boa Vista', 'Porto Alegre', 'RS'),
(18, 14299722, 7067, 'Rua das Flores', 'Centro', 'São Paulo', 'SP'),
(19, 29574552, 1997, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(20, 80951136, 7700, 'Rua XV de Novembro', 'Centro', 'Curitiba', 'PR'),
(21, 22584770, 9558, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ'),
(22, 53271968, 662, 'Avenida Boa Viagem', 'Boa Viagem', 'Recife', 'PE'),
(23, 54087719, 2917, 'Avenida Boa Viagem', 'Boa Viagem', 'Recife', 'PE'),
(24, 10599148, 5304, 'Rua das Flores', 'Centro', 'São Paulo', 'SP'),
(25, 17729435, 4135, 'Rua do Comércio', 'Jardim América', 'São Paulo', 'SP'),
(26, 34642960, 5069, 'Avenida Afonso Pena', 'Savassi', 'Belo Horizonte', 'MG'),
(27, 80377509, 817, 'Rua XV de Novembro', 'Centro', 'Curitiba', 'PR'),
(28, 29123166, 3251, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(29, 74027333, 4329, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(30, 28659936, 9581, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(31, 29394915, 1109, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(32, 74778722, 636, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(33, 29008521, 9914, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(34, 88458520, 313, 'Rua Felipe Schmidt', 'Centro', 'Florianópolis', 'SC'),
(35, 42120874, 798, 'Rua Marques de Leão', 'Barra', 'Salvador', 'BA'),
(36, 34157987, 1468, 'Avenida Afonso Pena', 'Savassi', 'Belo Horizonte', 'MG'),
(37, 14359533, 5820, 'Rua das Flores', 'Centro', 'São Paulo', 'SP'),
(38, 22739249, 4355, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ'),
(39, 29551227, 8772, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(40, 53315661, 5588, 'Avenida Boa Viagem', 'Boa Viagem', 'Recife', 'PE'),
(41, 29496498, 1414, 'Avenida Norte-Sul', 'Jardim Camburi', 'Vitória', 'ES'),
(42, 19328720, 1244, 'Rua do Comércio', 'Jardim América', 'São Paulo', 'SP'),
(43, 28986801, 8291, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(44, 29926160, 6682, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(45, 14645715, 3752, 'Rua das Flores', 'Centro', 'São Paulo', 'SP'),
(46, 28471907, 2471, 'Avenida das Américas', 'Barra', 'Rio de Janeiro', 'RJ'),
(47, 21851471, 1303, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ'),
(48, 43201832, 3082, 'Rua Marques de Leão', 'Barra', 'Salvador', 'BA'),
(49, 74296393, 3115, 'Avenida T-63', 'Setor Bueno', 'Goiânia', 'GO'),
(50, 21945337, 5804, 'Avenida Atlântica', 'Copacabana', 'Rio de Janeiro', 'RJ');


-- Inserção de dados fictícios na tabela clientes
INSERT INTO clientes (codigo_cliente, nome_cliente, sobrenome_cliente, codigo_tipo_cliente, tipo_cliente, cod_endereco)
VALUES
(1, 'João', 'Silva', 1, 'bronze', 1),
(2, 'Maria', 'Oliveira', 2, 'prata', 2),
(3, 'Pedro', 'Souza', 3, 'ouro', 3),
(4, 'Ana', 'Costa', 4, 'diamante', 4),
(5, 'Lucas', 'Ferreira', 1, 'bronze', 5),
(6, 'Fernanda', 'Gomes', 2, 'prata', 6),
(7, 'Rafael', 'Martins', 3, 'ouro', 7),
(8, 'Juliana', 'Santos', 4, 'diamante', 8),
(9, 'Carlos', 'Alves', 1, 'bronze', 9),
(10, 'Gabriela', 'Lima', 2, 'prata', 10),
(11, 'Ricardo', 'Barros', 3, 'ouro', 11),
(12, 'Patrícia', 'Ribeiro', 4, 'diamante', 12),
(13, 'Marcos', 'Pereira', 1, 'bronze', 13),
(14, 'Beatriz', 'Melo', 2, 'prata', 14),
(15, 'José', 'Carvalho', 3, 'ouro', 15),
(16, 'Carla', 'Nascimento', 4, 'diamante', 16),
(17, 'Leonardo', 'Rocha', 1, 'bronze', 17),
(18, 'Clara', 'Rezende', 2, 'prata', 18),
(19, 'André', 'Teixeira', 3, 'ouro', 19),
(20, 'Sofia', 'Cardoso', 4, 'diamante', 20),
(21, 'Vinícius', 'Campos', 1, 'bronze', 21),
(22, 'Luiza', 'Azevedo', 2, 'prata', 22),
(23, 'Rodrigo', 'Batista', 3, 'ouro', 23),
(24, 'Letícia', 'Moreira', 4, 'diamante', 24),
(25, 'Daniel', 'Vieira', 1, 'bronze', 25),
(26, 'Tainá', 'Almeida', 2, 'prata', 26),
(27, 'Henrique', 'Moura', 3, 'ouro', 27),
(28, 'Marcelo', 'Pinto', 4, 'diamante', 28),
(29, 'Isabela', 'Castro', 1, 'bronze', 29),
(30, 'Fábio', 'Araújo', 2, 'prata', 30),
(31, 'Elisa', 'Dias', 3, 'ouro', 31),
(32, 'Alexandre', 'Machado', 4, 'diamante', 32),
(33, 'Eduardo', 'Mendes', 1, 'bronze', 33),
(34, 'Larissa', 'Gonçalves', 2, 'prata', 34),
(35, 'Roberto', 'Vieira', 3, 'ouro', 35),
(36, 'Camila', 'Farias', 4, 'diamante', 36),
(37, 'Thiago', 'Ramos', 1, 'bronze', 37),
(38, 'Débora', 'Silveira', 2, 'prata', 38),
(39, 'Otávio', 'Nunes', 3, 'ouro', 39),
(40, 'Mariana', 'Correia', 4, 'diamante', 40),
(41, 'Bruno', 'Lacerda', 1, 'bronze', 41),
(42, 'Renata', 'Freitas', 2, 'prata', 42),
(43, 'Igor', 'Assis', 3, 'ouro', 43),
(44, 'Viviane', 'Barbosa', 4, 'diamante', 44),
(45, 'Hugo', 'Xavier', 1, 'bronze', 45),
(46, 'Fabiana', 'Aguiar', 2, 'prata', 46),
(47, 'Felipe', 'Monteiro', 3, 'ouro', 47),
(48, 'Natália', 'Lopes', 4, 'diamante', 48),
(49, 'Matheus', 'Peixoto', 1, 'bronze', 49),
(50, 'Priscila', 'Duarte', 2, 'prata', 50);


-- Retirada da restrição UNIQUE para tipo_produto da tabela produtos
ALTER TABLE produtos
DROP CONSTRAINT produtos_tipo_produto_key;


-- Inserção de dados fictícios na tabela produtos
INSERT INTO produtos (codigo_produto, tipo_produto, codigo_tipo_produto, nome_produto, descricao_produto, nome_diretor, email_diretor, codigo_diretor)
VALUES
(1, 'empréstimo', 101, 'Empréstimo Pessoal', 'Empréstimo para pessoa física com taxa fixa', 'José Almeida', 'jose.almeida@banco.com', 1),
(2, 'financiamento', 102, 'Financiamento Imobiliário', 'Financiamento para compra de imóveis', 'Maria Lima', 'maria.lima@banco.com', 2),
(3, 'investimento', 103, 'Fundo de Investimento', 'Fundo de renda fixa com baixa volatilidade', 'Carlos Sousa', 'carlos.sousa@banco.com', 3),
(4, 'cartão de crédito', 104, 'Cartão Platinum', 'Cartão de crédito com benefícios exclusivos', 'Ana Costa', 'ana.costa@banco.com', 4),
(5, 'seguros', 105, 'Seguro Vida', 'Seguro de vida para proteção familiar', 'José Almeida', 'jose.almeida@banco.com', 1),
(6, 'empréstimo', 106, 'Empréstimo Consignado', 'Empréstimo com desconto em folha de pagamento', 'Carlos Sousa', 'carlos.sousa@banco.com', 3),
(7, 'financiamento', 107, 'Financiamento Veicular', 'Financiamento para compra de veículos novos e usados', 'Ana Costa', 'ana.costa@banco.com', 4),
(8, 'investimento', 108, 'CDB (Certificado de Depósito Bancário)', 'Investimento de renda fixa em CDB', 'Maria Lima', 'maria.lima@banco.com', 2),
(9, 'cartão de crédito', 109, 'Cartão Gold', 'Cartão de crédito com cobertura nacional e internacional', 'José Almeida', 'jose.almeida@banco.com', 1),
(10, 'seguros', 110, 'Seguro Automóvel', 'Seguro completo para automóveis', 'Ana Costa', 'ana.costa@banco.com', 4),
(11, 'investimento', 111, 'Tesouro Direto', 'Investimento em títulos públicos federais', 'Carlos Sousa', 'carlos.sousa@banco.com', 3),
(12, 'seguros', 112, 'Seguro Residencial', 'Seguro para proteção da residência', 'Maria Lima', 'maria.lima@banco.com', 2),
(13, 'cartão de crédito', 113, 'Cartão Black', 'Cartão de crédito com benefícios e milhas aéreas', 'Carlos Sousa', 'carlos.sousa@banco.com', 3),
(14, 'financiamento', 114, 'Financiamento Rural', 'Financiamento para projetos rurais', 'José Almeida', 'jose.almeida@banco.com', 1),
(15, 'empréstimo', 115, 'Empréstimo Empresarial', 'Empréstimo para pessoa jurídica com taxas competitivas', 'Maria Lima', 'maria.lima@banco.com', 2);


-- Inserção de dados fictícios na tabela tel_cliente
INSERT INTO tel_cliente (id_tel_cliente, telefone_cliente)
VALUES
(1, '21987654321'),
(1, '21987654322'),
(2, '11976543210'),
(3, '11987651234'),
(3, '11987651235'),
(4, '21987654323'),
(5, '11987654321'),
(6, '21987654324'),
(7, '31987654325'),
(8, '51987654326'),
(8, '51987654327'),
(9, '61987654328'),
(10, '71987654329'),
(10, '71987654330'),
(11, '81987654331'),
(12, '21987654332'),
(13, '21987654333'),
(13, '21987654334'),
(14, '11987654335'),
(15, '21987654336'),
(15, '21987654337'),
(16, '31987654338'),
(17, '51987654339'),
(17, '51987654340'),
(18, '61987654341'),
(19, '71987654342'),
(19, '71987654343'),
(20, '81987654344'),
(21, '11987654345'),
(22, '21987654346'),
(23, '31987654347'),
(23, '31987654348'),
(24, '51987654349'),
(25, '61987654350'),
(25, '61987654351'),
(26, '71987654352'),
(27, '81987654353'),
(27, '81987654354'),
(28, '21987654355'),
(29, '11987654356'),
(30, '21987654357'),
(31, '31987654358'),
(31, '31987654359'),
(32, '51987654360'),
(33, '61987654361'),
(33, '61987654362'),
(34, '71987654363'),
(35, '81987654364'),
(35, '81987654365'),
(36, '21987654366'),
(37, '11987654367'),
(38, '21987654368'),
(39, '31987654369'),
(39, '31987654370'),
(40, '51987654371'),
(41, '61987654372'),
(42, '71987654373'),
(43, '81987654374'),
(44, '21987654375'),
(45, '11987654376'),
(45, '11987654377'),
(46, '31987654378'),
(47, '51987654379'),
(48, '61987654380'),
(49, '71987654381'),
(49, '71987654382'),
(50, '81987654383');


-- Inserção de dados fictícios na tabela transacoes
INSERT INTO transacoes (id_transacao, id_cliente, id_produto)
VALUES
(1, 1, 1),
(2, 1, 3),
(3, 2, 2),
(4, 2, 4),
(5, 3, 1),
(6, 3, 5),
(7, 4, 1),
(8, 5, 2),
(9, 6, 3),
(10, 6, 5),
(11, 7, 4),
(12, 8, 2),
(13, 8, 3),
(14, 9, 5),
(15, 10, 1),
(16, 11, 2),
(17, 12, 4),
(18, 13, 3),
(19, 14, 1),
(20, 15, 2),
(21, 16, 4),
(22, 16, 5),
(23, 17, 2),
(24, 18, 1),
(25, 19, 3),
(26, 20, 2),
(27, 21, 4),
(28, 22, 1),
(29, 23, 3),
(30, 24, 5),
(31, 25, 2),
(32, 26, 3),
(33, 27, 1),
(34, 28, 5),
(35, 29, 2),
(36, 30, 4),
(37, 31, 1),
(38, 32, 3),
(39, 33, 2),
(40, 34, 5),
(41, 35, 1),
(42, 36, 4),
(43, 37, 3),
(44, 38, 2),
(45, 39, 1),
(46, 40, 5),
(47, 41, 2),
(48, 42, 3),
(49, 43, 4),
(50, 44, 1);

-- 3) Liste os produtos do tipo investimento, ordenando-os pelo nome do diretor relacionado em ordem alfabética 
-- Use alias para mostrar o nome da coluna nome como "Produto" e da coluna diretor como "Nome do diretor".
-- A resposta da consulta não deve mostrar outras colunas de dados.
SELECT 
    nome_produto AS "Produto", 
    nome_diretor AS "Nome do diretor"
FROM 
    produtos
WHERE 
    tipo_produto = 'investimento'
ORDER BY 
    nome_diretor ASC;

-- 4) Liste todos os ids e clientes que realizaram uma quantidade de transações maior do que a média de transações 
-- encontradas no banco.
SELECT 
    c.codigo_cliente AS "ID do Cliente", 
    c.nome_cliente AS "Nome do Cliente",
    t.transacao_count AS "Quantidade de Transações"
FROM 
    clientes c
JOIN 
    (SELECT 
         id_cliente, 
         COUNT(*) AS transacao_count
     FROM 
         transacoes
     GROUP BY 
         id_cliente) t ON c.codigo_cliente = t.id_cliente
WHERE 
    t.transacao_count > (SELECT AVG(transacao_count) FROM 
                          (SELECT COUNT(*) AS transacao_count
                           FROM transacoes
                           GROUP BY id_cliente) AS subquery)
ORDER BY 
    c.codigo_cliente;

-- 5) Para cada tipo de produto, mostre a quantidade de produtos a ela associados. Caso uma categoria não tenha
-- nenhum produto a ela associada, esta categoria não deve aparecer no resultado final. A consulta deve estar ordenada 
-- por ordem alfabética dos tipos de produtos.
SELECT 
    tipo_produto AS "Tipo de Produto", 
    COUNT(codigo_produto) AS "Quantidade de Produtos"
FROM 
    produtos
GROUP BY 
    tipo_produto
HAVING 
    COUNT(codigo_produto) > 0
ORDER BY 
    tipo_produto ASC;

-- 7) Agora que você demonstrou que consegue ser mais do que um simples usuário do banco de dados, mostre separadamente 
-- cada um dos códigos DML necessários para cumprir cada uma das etapas a seguir:
-- Criação da tabela adimplencia
CREATE TABLE adimplencia (
    id2_cliente INT,
	id2_produto INT,
	adimplente BOOL,
    CONSTRAINT fk2_id_cliente
        FOREIGN KEY (id2_cliente)
        REFERENCES clientes (codigo_cliente),
    CONSTRAINT fk2_id_produto
        FOREIGN KEY (id2_produto)
        REFERENCES produtos (codigo_produto)
);
	
-- a) Inserir pelo menos 1 cliente alocado em um dos produtos na tabela produtos (todos com NULL na adimplente);
INSERT INTO adimplencia VALUES 
(47, 4, NULL), (45, 14, NULL), (37, 9, NULL), (19, 11, NULL), (15, 5, NULL), 
(20, 1, NULL), (16, 3, NULL), (7, 5, NULL), (33, 12, NULL), (40, 15, NULL), 
(33, 6, NULL), (34, 9, NULL), (43, 2, NULL), (35, 5, NULL), (19, 9, NULL), 
(24, 12, NULL), (3, 9, NULL), (5, 9, NULL), (8, 7, NULL), (5, 13, NULL), 
(6, 10, NULL), (17, 6, NULL), (26, 7, NULL), (1, 10, NULL), (50, 7, NULL), 
(3, 11, NULL), (20, 6, NULL), (44, 15, NULL), (36, 10, NULL), (21, 6, NULL);

-- b) Inserir pelo menos 2 produtos, não-alocados em qualquer um dos tipos de produtos na tabela produtos (todos com NULL 
-- na coluna tipo_produto e codigo_tipo_produto);
INSERT INTO produtos (codigo_produto, tipo_produto, codigo_tipo_produto, nome_produto, descricao_produto, nome_diretor, email_diretor, codigo_diretor)
VALUES
	(16, NULL, NULL, 'cartao roxinho', 'Cartao com super-transparencia. Voce no controle do dinheiro.', 'José Almeida', 'jose.almeida@banco.com', 1),
	(17, NULL, NULL, 'Financimento Lar-Doce-Lar', 'Financiamento para crédito habitacional e reformas', 'Carlos Sousa', 'carlos.sousa@banco.com', 3);

-- c) Atualizar a coluna adimplente da tabela adimplencia, de modo que os clientes associados a um produto com codigo 
-- menor que 7 estao adimplentes. Os demais estao inadimpentes.
UPDATE adimplencia
SET adimplente = 
   CASE WHEN id2_produto <= 7 THEN TRUE
   ELSE FALSE
END

SELECT * FROM adimplencia

-- d) Deletar os registros de adimplencia relacionados aos tipos de produto "Investimento", uma vez que não faz sentido
-- estar adimplente ou não nesta situação
DELETE 
FROM adimplencia
WHERE id2_produto in (3, 8, 11)

SELECT * FROM adimplencia