CREATE TABLE Produto (
    idProduto INT PRIMARY KEY,
    nome VARCHAR(100)
);

CREATE TABLE Venda (
    idVenda INT PRIMARY KEY,
    dataHora DATETIME,
    valorTotal DECIMAL(10,2)
);

CREATE TABLE ItemVenda (
    idItemVenda INT PRIMARY KEY,
    idVenda INT,
    idProduto INT,
    valorUnitario DECIMAL(10,2),
    quantidade INT,
    FOREIGN KEY (idVenda) REFERENCES Venda(idVenda),
    FOREIGN KEY (idProduto) REFERENCES Produto(idProduto)
);

INSERT INTO Produto (idProduto, nome) VALUES
    (1, 'Bolo de pote de chocolate'),
    (2, 'Bolo com recheio de maracujá'),
    (3, 'Surpresa de uva'),
    (4, 'Bombom trufado de ninho'),
    (5, 'Pudim de chocolate');

INSERT INTO Venda (idVenda, dataHora, valorTotal) VALUES
    (1, '2025-02-12 15:00:00', 75.00),
    (2, '2025-05-23 12:32:00', 270.00),
    (3, '2025-04-11 20:05:00', 120.00),
    (4, '2024-04-04 04:40:00', 80.00);

INSERT INTO ItemVenda (idItemVenda, idVenda, idProduto, valorUnitario, quantidade) VALUES
    (1, 1, 1, 15.00, 40),
    (2, 2, 2, 90.00, 10),
    (3, 3, 3, 20.00, 4),
    (4, 4, 2, 2.00, 40),
    (5, 2, 3, 4.00, 20);

-- https://1drv.ms/x/c/4a19299dbc5baa0f/EQ-qW7ydKRkggEpmBwAAAAABlRLpk3RaaQh9UpKbG2R8Ng?e=EvB3bf
-- Link da planilha com os dados
