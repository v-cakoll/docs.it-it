---
ms.openlocfilehash: c0c1c9c9d8e3aeb6f689f754d09b50b208b54112
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702265"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a>StringInfo e TextElementEnumerator ora sono conformi a UAX29

Prima di questa modifica, <xref:System.Globalization.StringInfo?displayProperty=fullName> non venivano <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> gestiti correttamente tutti i cluster grafema. Alcuni grafemi sono stati suddivisi in componenti costitutivi anziché essere mantenuti insieme. A questo punto, <xref:System.Globalization.StringInfo> ed <xref:System.Globalization.TextElementEnumerator> elabora i cluster grafema in base alla versione più recente dello standard Unicode.

Inoltre, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster grafema.

#### <a name="change-description"></a>Descrizione modifica:

Un cluster [grafema](https://www.unicode.org/glossary/#grapheme) o [grafema esteso](https://www.unicode.org/glossary/#extended_grapheme_cluster) è un singolo carattere percepito dall'utente che può essere costituito da più punti di codice Unicode. Ad esempio, la stringa contenente il carattere tailandese "Kam" ( :::no-loc text="กำ"::: ) è costituita dai due caratteri seguenti:

- :::no-loc text="ก":::(=' \u0e01') CARATTERE TAILANDESE KO KAI
- :::no-loc text=" ำ":::(=' \u0e33') CARATTERE TAILANDESE SARA AM

Quando viene visualizzato all'utente, il sistema operativo combina i due caratteri per formare il singolo carattere di visualizzazione (o grafema) "Kam" o :::no-loc text="กำ"::: . Emoji può anche essere costituito da più caratteri combinati per la visualizzazione in modo analogo.

> [!TIP]
> La documentazione di .NET usa talvolta il termine "elemento di testo" quando si fa riferimento a un grafema.

Le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e controllano le stringhe e restituiscono informazioni sui grafemi in essi contenute. In .NET Framework (tutte le versioni) e .NET Core 3. x e versioni precedenti, queste due classi usano la logica personalizzata che gestisce alcune classi combinate, ma non è completamente conforme allo [standard Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries). Ad esempio, le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e suddividono erroneamente il singolo carattere tailandese "Kam" nei componenti costitutivi anziché mantenerli insieme. Queste classi, inoltre, suddividono erroneamente il carattere emoji "🤷🏽 ♀️" in quattro cluster (disattivazione della persona, modificatore di tono della pelle, modificatore Gender e un combinatore invisibile) invece di mantenerli insieme come singolo cluster grafema.

A partire da .NET 5, <xref:System.Globalization.StringInfo> le <xref:System.Globalization.TextElementEnumerator> classi e implementano lo standard Unicode come definito da [Unicode Standard Annex \# 29, Rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html). In particolare, ora restituiscono [cluster grafema estesi](https://www.unicode.org/glossary/#extended_grapheme_cluster) per tutte le classi combinate.

Si consideri il codice C# seguente:

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

In .NET Framework e .NET Core 3. x e versioni precedenti, i grafemi vengono suddivisi e l'output della console è il seguente:

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

Inoltre, a partire da .NET 5, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster grafema.

Queste modifiche fanno parte di un set più ampio di miglioramenti Unicode e UTF-8 in .NET, inclusa un'API di enumerazione del cluster grafema estesa per completare le API di enumerazione dei valori scalari Unicode introdotte con il <xref:System.Text.Rune?displayProperty=fullName> tipo in .NET Core 3,0.

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0 Preview 1

#### <a name="recommended-action"></a>Azione consigliata

Non è necessario eseguire alcuna operazione. Le tue app si comporteranno automaticamente in modo più conforme agli standard in un'ampia gamma di scenari correlati alla globalizzazione.

#### <a name="category"></a>Category

Globalizzazione

#### <a name="affected-apis"></a>API interessate

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
