O #JUnit é uma ferramenta criada para facilitar a escrita de testes automatizados em software.

O Intellij nos fornece recursos para fazer isso de forma mais fácil.

![[Pasted image 20260610113130.png]]

![[Pasted image 20260610113153.png|283]]


Com a pasta *``lib``* criada, devemos inserir as seguintes bibliotecas nela:
● [junit-jupiter-api ](https://repo1.maven.org/maven2/org/junit/jupiter/junit-jupiter-api/6.0.0-M2/junit-jupiter-api-6.0.0-M2.jar)
● [junit-platform-commons](https://repo1.maven.org/maven2/org/junit/platform/junit-platform-commons/6.0.0-M2/junit-platform-commons-6.0.0-M2.jar) 

Podemos obter essas bibliotecas utilizando o site [http://mvnrepository.com/](http://mvnrepository.com/)

Não podemos esquecer de adicionar as bibliotecas recém inseridas como bibliotecas do projeto.
* Devemos coloca-las dentro da pasta lib 
* Selecionamos os dois arquivos e depois apertamos com botão direito do mouse e selecionar a opção **Add as Library**

![[Pasted image 20260610122655.png]]

* Após adicionarmos as bibliotecas nós podemos já inicializar os nossos teste.

Precisamos informar para o JUnit que a classe **ReservaTest** possui testes escritos. Fazemos isso utilizando a anotação **@Teste** isso para cada um dos testes.

## Métodos de Assert 
São os mais usados no dia a dia.

### `assertEquals()`

Verifica se os valores são iguais.

```Java
assertEquals(10, funcionario.calcularSalario());
```
### `assertNotEquals()`

Verifica se os valores são diferentes.

```Java
assertNotEquals(100, funcionario.calcularSalario());
```

### `assertNotEquals()`

Verifica se os valores são diferentes.

```Java
assertNotEquals(100, funcionario.calcularSalario());
```

### `assertTrue()`

Verifica se uma condição é verdadeira.

```Java
assertTrue(reserva.estaAtiva());
```

### `assertFalse()`

Verifica se uma condição é falsa.

```Java
assertFalse(reserva.estaCancelada());
```

## Exemplo mais avançado 
Neste caso criamos uma classe chamada **CalcularTotalTest**

Neste caso a classe Reserva possui um método que calcular o valor total da reserva.

Classe Reserva : 
```Java
public double calcularComCafeDaManha() {  
    long dias  = ChronoUnit.DAYS.between(getDataCheckIn(), getDataCheckOut());  
  
    double valorDiaria = dias * getValorDiaria();  
    double valorComCafeDaManha = valorDiaria * 5 / 100;  
  
    double total = valorComCafeDaManha + valorDiaria;  
  
    return total;  
}
```

Classe ReservaTest: 
```Java
@Test  
void calcularTotal()  {  
  
    Reserva reserva = new Reserva("1",  
            LocalDate.of(2026, 06, 26),  
            LocalDate.of(2026, 06, 29),  
            400.0,  
            10.0,  
            "Teste",  
            20,  
            true,  
            StatusReserva.CONCLUIDA  
    );  
    
    double total = reserva.calcularTotal();  
    assertEquals(1200.0, total);  
}
```

## Testar Métodos que retornam String 
Para testarmos métodos que retornam String devemos usar o ``assertEquals``, e apenas devemos comparar os textos.

```Java
@Override  
public String gerarDescrisaoFatura() {  
    return  
            "Check-In: " + getDataCheckIn() +  
                    " Check-Out: " + getDataCheckOut() +  
                    " Numéro de pessoas: " + getNumeroPessoas() +  
                    " Diárias: " + calcularNumeroDiarias() + " x R$ " + getValorDiaria() +  
                    " Café da manha: " + getIncluiCafeDaManha() +  
                    " Status: " + getStatusReserva() +  
                    " Total: R$ " + calcularTotal();  
}
```

Classe ReservaTest
```Java
@Test  
void gerarDescrisaoFatura() {  
    Reserva reserva = new Reserva("1",  
            LocalDate.of(2026, 06, 26),  
            LocalDate.of(2026, 06, 29),  
            400.0,  
            10.0,  
            "Teste",  
            20,  
            true,  
            StatusReserva.CONCLUIDA  
    );  
  
    String descricaoEsperada = "Check-In: 2026-06-26 Check-Out: 2026-06-29 Numéro de pessoas: 20 Diárias: 3 x R$ 400.0 Café da manha: true Status: CONCLUIDA Total: R$ 1200.0";  
    String descricaoAtual = reserva.gerarDescrisaoFatura();  
  
    assertEquals(descricaoEsperada, descricaoAtual);  
}
```
* Lembrando que a String esperada deve ser igual a atual. 
* Qualquer discrepância o teste não ira rodar.

## Fluxo do JUnit 
```
1. @Test          → avisa o JUnit que é um teste
2. Instancia      → cria o objeto com os dados que você quer testar
3. Chama o método → ACT — executa o que quer validar
4. assertEquals   → compara o esperado com o que o método retornou
```

E o ponto mais importante que você entendeu:

```
O teste NÃO implementa lógica.
O teste apenas VERIFICA se a lógica
que está na classe está correta.
```