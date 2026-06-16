É um método da ``List`` que percorre todos os elementos e remove aqueles que atendem a uma condição.

Sintaxe: 
```Java
lista.removeIf(elemento -> condicao);
```
* ``elemento`` = cada objeto da lista.
* ``condicao`` = regra que retorna ``true`` ou ``false``.
* Se retornar ``true``, o objeto é removido.
* Se retornar ``false`` , o objeto permanece.

**Classe Quarto:** 
```Java
public class Quarto {
    private String numeroQuarto;
    private boolean disponivel;

    public Quarto(String numeroQuarto, boolean disponivel) {
        this.numeroQuarto = numeroQuarto;
        this.disponivel = disponivel;
    }

    public String getNumeroQuarto() {
        return numeroQuarto;
    }

    public boolean isDisponivel() {
        return disponivel;
    }
}
```

**Classe Hotel 
```Java
import java.util.ArrayList;
import java.util.List;

public class Hotel {

    private List<Quarto> quartos = new ArrayList<>();

    public void adicionarQuarto(Quarto quarto) {
        quartos.add(quarto);
    }
```

Método usando ``RemoveIf()`` (Removendo por número)
```Java
    public boolean removerQuarto(String numero) {
        return quartos.removeIf(quarto -> quarto.getNumeroQuarto().equals(numero)
        );
    }
```

**Como ler o** ``removeIf`` :

```Java
quartos.removeIf(quarto -> quarto.getNumeroQuarto().equals(numero));
```

	Percorra todos os quartos da lista.  
	Se o número do quarto for igual ao número informado, remova ele da lista.