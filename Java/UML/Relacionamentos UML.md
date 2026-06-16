# Resumo dos símbolos de relacionamento UML

# 1. HERANÇA (Generalização)

Usado quando uma classe **herda** de outra.

## Símbolo

```text
─────▷
```

- linha contínua
    
- triângulo branco
    
- aponta para a classe pai
    

---

## Exemplo

```text
Tempestade ─────▷ EventoClimatico
```

Significa:

> Tempestade herda de EventoClimatico

Em Java:

```java
class Tempestade extends EventoClimatico
```

---

# 2. ASSOCIAÇÃO

Usado quando uma classe “usa” outra.

## Símbolo

```text
──────
```

(linha simples)

---

## Exemplo

```text
Sistema ───── Alerta
```

Significa:

> Sistema utiliza Alerta

---

# 3. AGREGAÇÃO

Relação “tem um”, mas os objetos podem existir separados.

## Símbolo

```text
◇─────
```

(losango branco)

---

## Exemplo

```text
Sistema ◇──── Sensor
```

Significa:

> Sistema possui sensores

Mas o sensor pode existir sozinho.

---

# 4. COMPOSIÇÃO

Relação forte de dependência.

Se o objeto principal morrer, os outros também.

## Símbolo

```text
◆─────
```

(losango preto)

---

## Exemplo

```text
Casa ◆──── Quarto
```

Significa:

> O quarto faz parte da casa

Se a casa deixa de existir, o quarto também.

---

# 5. DEPENDÊNCIA

Quando uma classe apenas usa outra temporariamente.

## Símbolo

```text
- - - -▷
```

(linha tracejada)

---

## Exemplo

```text
Relatorio - - -▷ Impressora
```

---

# O QUE VOCÊ USA NO SEU PROJETO

No seu projeto climático:

## Você PRECISA principalmente de:

# HERANÇA

```text
Tempestade ─────▷ EventoClimatico
Seca ───────────▷ EventoClimatico
```

---

# Dica rápida para memorizar

|Relacionamento|Símbolo|Ideia|
|---|---|---|
|Herança|▷|“é um”|
|Associação|─|“usa”|
|Agregação|◇|“tem um”|
|Composição|◆|“faz parte de”|
|Dependência|- -▷|“depende de”|
