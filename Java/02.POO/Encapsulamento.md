O encapsulamento é baseado em quatro conceitos fundamentais

Os atributos ficam protegidos e o acesso é feito por métodos.

## Exemplo

```Java 
public class ContaBancaria {    
	private double saldo;    
	
	public double getSaldo() 
	{        
		return saldo;   
	}    
	
	public void depositar(double valor) 
	{        
		saldo += valor;    
	}
}
```

Uso:

```Java 
ContaBancaria conta = new ContaBancaria();  
  
conta.depositar(100);  
  
System.out.println(conta.getSaldo());
```

## Por que usar?

Sem encapsulamento:

```
public double saldo;
```

Alguém poderia fazer:

```
conta.saldo = -5000;
```

O que pode ser inválido.

Com encapsulamento:

```
private double saldo;
```

A classe controla as alterações.

---

## Modificadores de acesso

### private

Acessível apenas dentro da própria classe.

```
private String nome;
```

---

### protected

Acessível na própria classe e nas filhas.

```
protected double intensidade;
```

---

### public

Acessível de qualquer lugar.

```
public void calcular() {}
```