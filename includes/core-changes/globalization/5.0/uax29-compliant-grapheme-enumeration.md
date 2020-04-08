---
ms.openlocfilehash: f131933f3cf7890939854c46f115e8deb8da1cc2
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888170"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a>StringInfo e TextElementEnumerator sono ora conformi a UAX29

Prima di questa <xref:System.Globalization.StringInfo?displayProperty=fullName> <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> modifica, e non gestito correttamente tutti i cluster di grafemi. Alcuni grafemi sono stati divisi nelle loro componenti costituenti invece di essere tenuti insieme. A <xref:System.Globalization.StringInfo> questo <xref:System.Globalization.TextElementEnumerator> punto, ed elaborare i cluster di grafemi in base all'ultima versione dello standard Unicode.

Inoltre, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster di grafemi.

#### <a name="change-description"></a>Descrizione modifica:

Un cluster di [grafemi](https://www.unicode.org/glossary/#grapheme) o [grafemi esteso](https://www.unicode.org/glossary/#extended_grapheme_cluster) è un singolo carattere percepito dall'utente che può essere costituito da più punti di codice Unicode. Ad esempio, la stringa contenente il carattere tailandese "kam" (:::no-loc text="กำ":::) è costituita dai due caratteri seguenti:

- :::no-loc text="ก":::('u0e01') THAI CHARACTER KO KAI
- :::no-loc text=" ำ":::(Sezione : ''u0e33'') THAI CHARACTER SARA AM

Quando viene visualizzato all'utente, il sistema operativo combina i due caratteri per formare il :::no-loc text="กำ":::singolo carattere di visualizzazione (o grafema) "kam" o . Le emoji possono anche essere costituite da più caratteri combinati per la visualizzazione in modo simile.

> [!TIP]
> La documentazione di .NET a volte utilizza il termine "elemento di testo" quando si fa riferimento a un grafema.

Le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e esaminano le stringhe e restituiscono informazioni sui grafemi che contengono. In .NET Framework (tutte le versioni) e .NET Core 3.x e versioni precedenti, queste due classi utilizzano la logica personalizzata che gestisce alcune classi di combinazione ma non sono completamente conformi allo [standard Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries). Ad esempio, <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> le classi e suddividono erroneamente il singolo carattere tailandese "kam" nei relativi componenti costitutivi anziché tenerli insieme. Queste classi anche erroneamente diviso il carattere emoji "🤷🏽 ♀️" in quattro gruppi (persona che shrugging, modificatore di tono della pelle, modificatore di genere, e un combinatore invisibile) invece di tenerli insieme come un singolo cluster di grafemi.

A partire da .NET 5, le <xref:System.Globalization.StringInfo> classi e <xref:System.Globalization.TextElementEnumerator> implementano lo standard Unicode come definito da Unicode Standard [Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html). In particolare, ora restituiscono cluster di [grafemi estesi](https://www.unicode.org/glossary/#extended_grapheme_cluster) per tutte le classi combinate.

Si consideri il seguente codice in C:

```cs
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

In .NET Framework e .NET Core 3.x e versioni precedenti, i grafemi vengono suddivisi e l'output della console è il seguente:

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

In .NET 5 e versioni successive, i grafemi vengono mantenuti insieme e l'output della console è il seguente:

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

Inoltre, a partire da .NET 5, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo , che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster di grafemi.

Queste modifiche fanno parte di un set più ampio di miglioramenti Unicode e UTF-8 in .NET, tra cui un'API di <xref:System.Text.Rune?displayProperty=fullName> enumerazione del cluster grapheme estesa per completare le API di enumerazione del valore scalare Unicode introdotte con il tipo in .NET Core 3.0.

#### <a name="version-introduced"></a>Versione introdotta

Anteprima 1 di .NET 5.0

### <a name="recommended-action"></a>Azione consigliata

Non è necessario eseguire alcuna operazione. Le app si comporterà automaticamente in modo più conforme agli standard in una varietà di scenari correlati alla globalizzazione.

### <a name="category"></a>Category

Globalizzazione

### <a name="affected-apis"></a>API interessate

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
