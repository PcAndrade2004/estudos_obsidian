A herança em Java, é u, dos pilares da programação orientada a objetos

Ela permite com que as classes herdem atributos e métodos de outra classe, evitando repetições de código e criando um relação deles. 
## Estrutura Básica

Classe pai (superclasse):

```
public class Animal {    private String nome;    public Animal(String nome) {        this.nome = nome;    }    public void emitirSom() {        System.out.println("Som genérico");    }    public String getNome() {        return nome;    }}
```

Classe filha (subclasse):

```
public class Cachorro extends Animal {    public Cachorro(String nome) {        super(nome);    }}
```

A palavra:

```
extends
```

significa:

> "Cachorro herda de Animal"
# O que é herdado?

A classe filha herda:

✅ Métodos

✅ Atributos acessíveis

✅ Comportamentos

Exemplo:

```
Cachorro cachorro = new Cachorro("Rex");System.out.println(cachorro.getNome());
```

Mesmo sem criar o método `getNome()` em `Cachorro`, ele funciona porque foi herdado de `Animal`.

---

# O papel do super()

Quando uma classe herda de outra, o construtor da classe pai precisa ser executado.

Por isso usamos:

```
super(...)
```

Exemplo:

```
public Cachorro(String nome) {    super(nome);}
```

Isso chama:

```
public Animal(String nome)
```

---

# Sobrescrita de Métodos (Override)

Muitas vezes a classe filha precisa modificar um comportamento da classe pai.

Usamos:

```
@Override
```

Exemplo:

```
public class Cachorro extends Animal {    public Cachorro(String nome) {        super(nome);    }    @Override    public void emitirSom() {        System.out.println("Au Au");    }}
```

Agora:

```
Cachorro cachorro = new Cachorro("Rex");cachorro.emitirSom();
```

Saída:

```
Au Au
```