Em Java, ``List`` é uma estrutura de coleção usada para armazenar vários objetos em sequência. 

## O que é uma List?

Uma ``List`` funciona como uma **lista dinâmica de objetos**.
```Java
[Tempestade]  
[Enchente]  
[Seca]  
[Ciclone]
```

A List: 
* cresce automaticamente
* é mais fácil de manipular
* possui métodos prontos

## Import necessário
Para usarmos uma ``List``, precisamos importar algumas classe Java.
```Java 
import java.util.List;
import java.util.ArrayList;
```

## List 
``List`` é considerada uma interface.

### Criando #List com Tipos 
Criamos uma ``List`` da seguinte forma: 
```Java 
List<String> nomes = new ArrayList<>();
```


```Java
import java.util.List;
import java.util.ArrayList;

public class Teste {    
public static void main(String[] args) {   
     
List<String> cidades = new ArrayList<>();        

cidades.add("São Paulo");        
cidades.add("Rio de Janeiro");        
cidades.add("Curitiba");        

System.out.println(cidades);    }}
```
Saída:

```
[São Paulo, Rio de Janeiro, Curitiba]
```
Neste caso:
```Java
List<String> define o tipo de coleção
```
* Significa que o tipo de retorno e *String*

### Criando #List com objetos 

```Java
List<Alerta> alertas;
```

significa:

```
Uma lista de objetos do tipo Alerta
```

Exemplos: 
```Java 
public class Alerta {    

	private String tipo;    
	private int nivel;  
	  
	public Alerta(String tipo, int nivel) {        
		this.tipo = tipo;        
		this.nivel = nivel;    
	}   
	 
	public String getTipo() 
	{        
		return tipo;    
	}    
	
	public int getNivel() 
	{        
		return nivel;    
	}

}
```

```Java 
import java.util.List;
import java.util.ArrayList;

public class Sistema {    
	private List<Alerta> alertas;   
	public Sistema() {        
		alertas = new ArrayList<>();    
	}    
	
	public void adicionarAlerta(Alerta alerta) 
	{        
		alertas.add(alerta);    
	}    
	
	public void listarAlertas() 
	{        
		for (Alerta a : alertas) 
	{            
	
	System.out.println(a.getTipo());            
	System.out.println(a.getNivel());        
}
```
# List com #Objetos em Java com atributo

Em Java, usamos `List` quando precisamos armazenar vários objetos da mesma classe.
## Declaração da List

```Java
private List<Tipo> lista;
```

Exemplo:

```Java
private List<EventoClimatico> eventosClimaticos;
```
## Imports necessários

```Java
import java.util.List;
import java.util.ArrayList;
```
## Inicialização da List

A `List` precisa ser inicializada, normalmente no construtor.

```Java
public Classe() {    
	lista = new ArrayList<>();
}
```

Exemplo:

```Java
public Sistema() 
{    
	eventosClimaticos = new ArrayList<>();
}
```
## Por que inicializar?

Sem inicializar:

```Java
private List<EventoClimatico> eventosClimaticos;
```

a lista fica:

```Java
null
```

Então isso:

```Java
eventosClimaticos.add(evento);
```

gera:

```Java
NullPointerException
```
## Estrutura padrão mais usada

```Java
private List<Tipo> lista;

public Classe() {    
	lista = new ArrayList<>();
}
```

## Adicionando Objetos
```Java 
lista.add(objeto);
```

Exemplo:
```Java 
eventosClimaticos.add(evento);
```

# Métodos de List 
# add()

Adiciona elemento na lista.

```
nomes.add("Paulo");
```

---

# add(posicao, elemento)

Adiciona em posição específica.

```
nomes.add(0, "Carlos");
```

---

# get()

Retorna elemento pelo índice.

```
nomes.get(0);
```

---

# set()

Substitui elemento.

```
nomes.set(0, "Ana");
```

---

# remove()

Remove elemento.

## Por índice

```
nomes.remove(0);
```

## Por objeto

```
nomes.remove("Paulo");
```

---

# size()

Retorna quantidade de elementos.

```
nomes.size();
```

---

# contains()

Verifica se existe na lista.

```
nomes.contains("Ana");
```

Retorna:

```
true ou false
```

---

# isEmpty()

Verifica se a lista está vazia.

```
nomes.isEmpty();
```

---

# clear()

Remove todos os elementos.

```
nomes.clear();
```

---

# indexOf()

Retorna posição do elemento.

```
nomes.indexOf("Ana");
```

---

# lastIndexOf()

Retorna última ocorrência.

```
nomes.lastIndexOf("Ana");
```