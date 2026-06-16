Em Java ``enum`` (enumeration) é um tipo especial usado para representar um conjunto fixo de constantes.

Exemplo clássico: 
```Java
enum DiaSemana {
	SEGUNDA,
	TERCA,
	QUARTA,
	QUINTA,
	SEXTA,
	SABADO,
	DOMINGO
}
```

* Aqui estamos dizendo que o ``DiaSemana`` só pode ter um desses valores.

Assim pode evitar alguns erros de digitação:
```Java
String dia = "Seundna"; // ERRO DE DIGITAÇÃO
```

##  Criando um #enum
```Java 
public enum NivelRisco {
	BAIXO,
	MEDIO,
	ALTO
}
```

### Usando no código
```Java
NivelRisco nivel = NivelRisco.Baixo;

System.out.println(nivel);

// SAÍDA 
BAIXO
```

### Aonde usar os #ENUM
Podemos usar o ENUM em muitos sentidos: 
* estados 
* categorias 
* níveis 
* tipos fixos
* classificações

# Enum é uma classe
Muita gente não sabe disso:

Um `enum` internamente é uma classe especial.

Por isso ele pode ter:
- atributos
- construtores
- métodos
- encapsulamento

## Enum com descrição 
É muito útil em sistemas reais: 
```Java 
public enum IntensidadeTempestade {

    FRACA("Pouco perigosa"),
    MODERADA("Atenção"),
    FORTE("Risco alto"),
    SEVERA("Perigo extremo");

    private String descricao;

    IntensidadeTempestade(String descricao) {
        this.descricao = descricao;
    }

    public String getDescricao() {
        return descricao;
    }
}

// COMO USAR 
System.out.println(
    IntensidadeTempestade.SEVEREA.getDescricao()
);
```

# Métodos importantes do enum

## `values()`

Retorna todos os valores do enum.

```
for (NivelRisco n : NivelRisco.values()) {    System.out.println(n);}
```

Saída:

```
BAIXOMEDIOALTO
```

## `valueOf()`

Transforma texto em enum.

```
NivelRisco risco = NivelRisco.valueOf("ALTO");
```