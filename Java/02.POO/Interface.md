Uma interface é um contrato. 

Ele define *o que uma classe deve fazer*, *mas não como ela faz*

```
Se você implementar esta interface,
você DEVE implementar estes métodos.
```

## Sintaxe Básica 
Interface: 

```Java
public interface Calculavel() {
	double calcular();
}
```

Caso implementado: 
```Java 
public class Imposto implements Calculavel() {
	@Override 
	public double calcular() {
		return 100;
	}
}
```

A palavra-chave:

```
implements
```

significa:

> "Estou assumindo o contrato desta interface."

## Porque usar Interface 
Sem Interface : 
```Java 
public class Imposto {
	public double calcular() {
		return 100;
	}
}
```
* Funciona, mas não existe garantia de que outras classes terão o método ``calcular()``

Com interface:

```Java 
public interface Calculavel 
{    
	double calcular();
}
```

> Todas as classes que implementarem essa interface serão obrigadas a possuir esse método.

## Quando usar Interface?

Quando você quer definir um comportamento.

Exemplos clássicos:

```Java
Comparable
Runnable
Serializable
AutoCloseable
```

### Um exemplo real

Interface:

```Java
public interface Pagamento {   
	 void pagar(double valor);
 }
```

Implementações:

```Java
public class Pix implements Pagamento 
{    
	@Override    
	public void pagar(double valor) {        
		System.out.println("Pagamento via PIX");    
		
	}
}
```

```Java
public class CartaoCredito implements Pagamento {    @Override    public void pagar(double valor) {        System.out.println("Pagamento via Cartão");    }}
```

Uso:

```Java
Pagamento pagamento = new Pix();pagamento.pagar(500);
```

Depois:

```Java
pagamento = new CartaoCredito();pagamento.pagar(500);
```

