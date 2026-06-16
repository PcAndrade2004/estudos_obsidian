O ``String.format``  serve para formatar textos, incluindo números ``double`` 
* Limitar casas decimais
* arredondar valores
* exibir números de forma bonita

# Sintaxe básica

```Java

String valor = 21;


String.format("formato", valor);

// SAÍDA 
formato 21
```

# Arredondando para 2 casas decimais

```Java
double numero = 15.6789;
String resultado = String.format("%.2f", numero);

System.out.println(resultado);
```

Saída:

```
15.68
```

Explicação do ``%.2f``
``%`` -> inicio da formatação 
``.2`` -> quantidade de casas decimais
``f`` -> números decimal 

