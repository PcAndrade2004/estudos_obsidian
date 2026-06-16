O `DateTimeFormatter` é uma classe do Java (pacote `java.time.format`) usada para converter objetos de data/hora em texto (formatar) e texto em objetos de data/hora (analisar). 

*Converter de String para Objeto de Data-Hora*

Você pode usar um padrão personalizado com `ofPattern()` ou constantes predefinidas (como `ISO_LOCAL_DATE`). 

```Java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Exemplo {
    public static void main(String[] args) {
        // Obter a data e hora atual
        LocalDateTime agora = LocalDateTime.now();

        // 1. Criar um formatador personalizado
        DateTimeFormatter formatador = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");

        // 2. Formatar (Data para String)
        String dataFormatada = agora.format(formatador);
        System.out.println("Data formatada: " + dataFormatada);

        // 3. Analisar (String para Data)
        String dataTexto = "25/12/2026 15:30:00";
        LocalDateTime dataParseada = LocalDateTime.parse(dataTexto, formatador);
        System.out.println("Data parseada: " + dataParseada);
    }
}
```

### Usando o #ofPattern

Ao construir padrões com `ofPattern`, você utiliza letras específicas para representar cada parte da data e hora:

| Símbolo          | Significado             | Exemplo |
| ---------------- | ----------------------- | ------- |
| `yyyy` ou `uuuu` | Ano com 4 dígitos       | `2026`  |
| `MM`             | Mês em número           | `06`    |
| `MMM`            | Mês abreviado (texto)   | `Jun`   |
| `MMMM`           | Mês por extenso (texto) | `Junho` |
| `dd`             | Dia do mês              | `01`    |
| `HH`             | Hora no formato 24h     | `18`    |
| `mm`             | Minuto                  | `19`    |
| `ss`             | Segundo                 | `59`    |
