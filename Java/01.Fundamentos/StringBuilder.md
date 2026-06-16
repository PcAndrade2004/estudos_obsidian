
# StringBuilder em Java
## Por que usar?

`String` é imutável.

Toda vez que você faz:

```java
texto += "novo";
```

o Java cria um novo objeto.

O `StringBuilder` evita isso.

---

## Criando

```java
StringBuilder sb = new StringBuilder();
```

---

## Método principal

## `append()`

Adiciona texto.

```java
sb.append("Olá");
```

---

## Convertendo para String

```java
String texto = sb.toString();
```

## Exemplo

```java
StringBuilder sb = new StringBuilder();

sb.append("Java");
sb.append(" ");
sb.append("POO");

System.out.println(sb);
```

Saída:

```java
Java POO
```

---

# Métodos úteis

|Método|Função|
|---|---|
|`append()`|adiciona texto|
|`insert()`|insere texto|
|`delete()`|remove texto|
|`replace()`|troca texto|
|`reverse()`|inverte texto|
|`toString()`|transforma em String|

---

# Quando usar

✅ Loops  
✅ Muitas concatenações  
✅ Relatórios  
✅ Montagem de textos grandes
## Resumo rápido

```java
StringBuilder sb = new StringBuilder();

sb.append("Texto");

String resultado = sb.toString();
```

`StringBuilder` = forma rápida e eficiente de manipular textos em Java.