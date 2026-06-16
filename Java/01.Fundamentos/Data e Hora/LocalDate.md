## Operações Importantes com data-hora 
* Instanciação 
	* (agora) - Data-hora
	* Texto ISO 8601 - Data-hora
	* Texto formato customizado - Data-hora
	* dia, mês, ano , [horário] - Data-hora

* Formatação 
	* Data-hora - Texto ISO 8601
	* Data-hora - Texto formato customizado

* Obter dados de uma data-hora local
	* Data-hora-local - dia, mês, ano, horário

* Converter data-hora global para local
	* Data-hora global, timezone (sistema local) - Data-hora local

* Cálculos com data-hora
	* Data-hora +/- tempo - Data-hora
	* Data-hora 1, Data-hora 2 - Duração

## Instanciando data-hora do (agora)
### Obtendo *Data*
```Java
// instânciando Data (agora)
   LocalDate d01 = LocalDate.now(); 
```
* Ele pegou a data e hora do meu sistema e estanciou um objeto do tipo Local Date.
* Ele gera ate com a fração do horário.
### Obtendo data e hora 
```Java 
// Instanciando data e hora (agora)
LocalDateTime d02 = LocalDateTime.now():

SAIDA
d02 = 2026-06-07T14:08:40.837706600
```
### Usando o *Instant *
```Java
// Usando o Instant
Instant d03 = Instant .now();

SAIDA
d03 = 2026-06-07T17:08:40.838705300Z
```
* No final ele tem o ```z``` no final indica que isso é uma data GMT
* Caso eu queira exibir está data e hora para o usuário eu tenho que converter para data hora da minha maquina.
### Texto ISO 8601 e gerar data a partir de um texto 
```Java
LocalDate d04 = LocalDate.parse("2020-04-04");  
System.out.println("d04 = "+ d04);

SAIDA
d04 = 2020-04-04
```
* Ele converte de um formato Texto para um objeto data-hora.
### Texto ISO 8601 e gerar data e hora a partir dele
```Java
LocalDateTime d05 = LocalDateTime.parse("2020-04-04T14:05:26");  
System.out.println("d05 = " + d05);

SAIDA
d05 = 2020-04-04T14:05:26
```
* Lembrando que temos que adicionar o ```T```

### Texto formato customizado - Data-hora
```Java 
LocalDate d06 = LocalDate.parse("20/04/2004");

------------------------------------------------------------------------------------- 

Exception in thread "main" java.time.format.DateTimeParseException: Text '20/04/2004' could not be parsed at index 0
	at java.base/java.time.format.DateTimeFormatter.parseResolved0(DateTimeFormatter.java:2108)
	at java.base/java.time.format.DateTimeFormatter.parse(DateTimeFormatter.java:2010)
	at java.base/java.time.LocalDate.parse(LocalDate.java:435)
	at java.base/java.time.LocalDate.parse(LocalDate.java:420)
	at Main.main(Main.java:29)
```

* Neste caso gera uma exceção pois não especificamos como deve ser interpretado a data-hora no formato  ( DD - MM - YYYY )
* Para especificarmos devemos utilizar um tipo especial chamado [[Duvidas/DateTimeFormatter]]
```Java
LocaTimeFormatter ftm1 = DateTimeFormatter.ofPattern("dd/MM/yyyy");
LocalDate d06 = LocalDate.parse("20/04/2004", ftm1);
```
* Neste caso eu devo passar como *argumento o objeto fmt1 que é meu DateTimeFormatter*

## Adicionando datas 
### Adicionar dias
```Java
LocalDate hoje = LocalDate.now();

LocalDate daquiSeteDias = hoje.plusDays(7);  
  
System.out.println("Hoje: " + hoje);  
System.out.println("DaquiSeteDias: " + daquiSeteDias);
```
### Removendo dias 
```Java
// Diminuindo o ano  
LocalDate mes = hoje.minusDays(7);  
System.out.println("Mes: " + mes);
```

### Adicionar meses
```Java
LocalDate mes = hoje.plusMonths(7);
System.out.println("Adicionando mês: " + mes);
```

### Adicionar anos
```Java
LocalDate proximoAno = hoje.plusYears(1);
```

## Descobrir a quantidade de dias #ChronoUnit
### ChronoUnit
Muito utilizado em sistemas reais.

```Java
LocalDate inicio = LocalDate.of(2026, 1, 1);
LocalDate fim = LocalDate.of(2026, 6, 8);

long dias = ChronoUnit.DAYS.between(inicio, fim);

System.out.println(dias);
```
Resultado:
```Java
158
```
## Diferença entre horários 
### Duration
Usado para horas, minutos e segundos.
```Java
LocalTime inicio = LocalTime.of(8, 0);
LocalTime fim = LocalTime.of(17, 30);

Duration duracao = Duration.between(inicio, fim);

System.out.println(duracao.toHours());
```

Resultado:
```Java
9
```
Para obter minutos:

```Java
System.out.println(duracao.toMinutes());
```
Resultado:
```Java
570
```

## Comparar Datas 
 Em Java, podemos comprar datas da seguinte maneira.
Podemos usar quando queremos fazer alguma validação. Quando queremos saber quando uma data não pode ser anterior da outra.

* Antes => ``data1.isBefore(data2);``
* Depois => ``data1.isAfter(data2);``
* Igual => ``data1.isEquals(data2);``

```Java 
if(checkOut.isBefore(checkIn)) {
	throw new IllegalArgumentException(
	"Check-out não pode ser anterior ao check-in"
	)
}
```
* Neste caso acima estamos validando, caso o dia de saída seja antes da chegada ele ira exibir esta mensagem de erro.

![[Comprar-Datas.png]]
## Somando e subtraindo horas 
```Java
LocalDateTime agora = LocalDateTime.now();

LocalDateTime daquiADuasHoras = agora.plusHours(2);

LocalDateTime menosDeTrintaMinutos = agora.minuts(30);
```

