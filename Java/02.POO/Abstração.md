Em Java, uma classe abstrata e uma classe que serve como **modelo/base** para outras classes

Ela é **usada quando várias classes possuem características em comum**, mas cada uma **implementa certos comportamentos de maneira diferentes**.

# Estrutura básica

``` Java 
public abstract class Animal {    

	String nome; 
   
public void dormir() {        
	System.out.println("O animal está dormindo");    
}    

	public abstract void emitirSom();

}
```

## Quando devemos usar 
Usamos quando dizemos que : 
* essa classe NÃO pode ser instanciada 
* ela foi criada para ser herdada
* e ela pode possuir 
	* métodos normais 
	* atributos
	* construtores 
	* métodos abstratos

## Métodos abstratos 
* NÃO possui implementação 
* obriga as classes filhas a implementarem 
```Java 
public abstract void emitirSom();
```

# Quando usar classe abstrata

Use quando existir:

- comportamento em comum
- atributos em comum
- mas algumas **ações precisam ser diferentes**
