As chaves estrangeira usamos quando as tabelas possuem algum relacionamento.


## Criando Foreign Key coma  tabela 
* Podemos criar a Foreign Key junto com a criação da tabela:

```SQL
CREATE TABLE tb_cliente
(
	id_cliente
	CPF VARCHAR2(20),
	nm_cliente VARCHAR2(50),
	EMAIL VARCHAR2(100)

	CONSTRAINT tb_aluno 
		 PRIMARY KEY (id_cliente)
);
```


```SQL
CREATE TABLE tb_pedido
(
	id_pedido NUMBER, 
	id_cliente NUMBER,
	
	CONSTRAINT pk_pedido
		PRIMARY KEY (id_pedido)
		
	CONTRAINT fk_pedidos_cliente
		FOREIGN KEY (id_cliente)
		REFERENCES tb_cliente(id_cliente);
		
);
```

## Adicionando Chave Estrangeira (FK)
```SQL
ALTER TABLE tb_aluno 
ADD CONSTRAINT id_aluno_fk FOREIGN KEY (id_aluno)
REFERENCES tb_aluno (id_aluno);
```

### Significado :
*<font color="#ff0000"> Neste caso um pedido pertence a um cliente</font>