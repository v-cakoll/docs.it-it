---
title: Come cercare stringhe (Guida a C#)
ms.date: 02/21/2018
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with String methods
- strings [C#], searching with regular expressions
ms.assetid: fb1d9a6d-598d-4a35-bd5f-b86012edcb2b
ms.openlocfilehash: 34f9f2df11f9b7c51fcec2f8475a50ccf4c5e220
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324123"
---
# <a name="how-to-search-strings"></a>Come cercare stringhe

È possibile usare due strategie principali per la ricerca del testo nelle stringhe. I metodi della classe <xref:System.String> consentono di cercare testo specifico. Le espressioni regolari consentono di cercare modelli nel testo.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Il tipo [string](../language-reference/builtin-types/reference-types.md#the-string-type), che è un alias per la classe <xref:System.String?displayProperty=nameWithType>, fornisce diversi metodi utili per la ricerca dei contenuti di una stringa. Alcuni di questi sono <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A>, <xref:System.String.EndsWith%2A>, <xref:System.String.IndexOf%2A> e <xref:System.String.LastIndexOf%2A>. La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> offre un vocabolario avanzato per la ricerca di modelli nel testo. In questo articolo vengono illustrate queste tecniche e viene spiegato come scegliere il metodo migliore per le specifiche esigenze.

## <a name="does-a-string-contain-text"></a>Una stringa contiene testo?

I <xref:System.String.Contains%2A?displayProperty=nameWithType> <xref:System.String.StartsWith%2A?displayProperty=nameWithType> metodi, e <xref:System.String.EndsWith%2A?displayProperty=nameWithType> cercano un testo specifico in una stringa. Nell'esempio seguente vengono illustrati ognuno di questi metodi e una variante che utilizza una ricerca senza distinzione tra maiuscole e minuscole:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet1":::

L'esempio precedente dimostra un aspetto importante per l'uso di questi metodi. Le ricerche **fanno distinzione tra maiuscole e minuscole** per impostazione predefinita. Usare il <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> valore di enumerazione per specificare una ricerca senza distinzione tra maiuscole e minuscole.

## <a name="where-does-the-sought-text-occur-in-a-string"></a>Qual è la posizione del testo cercato in una stringa?

Anche i metodi <xref:System.String.IndexOf%2A> e <xref:System.String.LastIndexOf%2A> consentono di cercare testo nelle stringhe. Questi metodi restituiscono la posizione del testo cercato. Se il testo non viene trovato, restituiscono `-1`. L'esempio seguente mostra una ricerca della prima e dell'ultima occorrenza della parola "methods" e visualizza il testo che intercorre.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet2":::

## <a name="finding-specific-text-using-regular-expressions"></a>Ricerca di testo specifico con espressioni regolari

La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> può essere usata per eseguire la ricerca di stringhe. Queste ricerche possono usare modelli di testo semplici, ma anche piuttosto complicati.

L'esempio di codice seguente cerca la parola "the" o "their" in una frase, ignorando la combinazione di maiuscole e minuscole. Il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> esegue la ricerca. È necessario passare la stringa da cercare e i criteri di ricerca. In questo caso, un terzo argomento specifica una ricerca senza distinzione tra maiuscole e minuscole. Per altre informazioni, vedere <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

I criteri di ricerca descrivono il testo da cercare. La tabella seguente descrive ogni elemento dei criteri di ricerca. Nella tabella seguente viene usato il singolo oggetto `\` , che deve essere preceduto da un carattere di escape come `\\` in una stringa C#.

| Modello  | Significato                          |
|----------|----------------------------------|
| `the`    | corrisponde al testo "the"             |
| `(eir)?` | corrisponde a 0 o 1 occorrenza di "eir" |
| `\s`     | corrisponde a un carattere spazio vuoto    |

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet3":::

> [!TIP]
> I metodi `string` rappresentano in genere una scelta migliore per cercare stringhe esatte. Le espressioni regolari sono migliori quando si cerca un modello in una stringa di origine.

## <a name="does-a-string-follow-a-pattern"></a>Una stringa segue un modello?

Il codice seguente usa le espressioni regolari per convalidare il formato di ogni stringa in una matrice. Per la convalida è necessario che ogni stringa abbia il formato di un numero di telefono costituito da tre gruppi di cifre separate da trattini, di cui i primi due gruppi contengono tre cifre e il terzo ne contiene quattro. I criteri di ricerca usano l'espressione regolare `^\\d{3}-\\d{3}-\\d{4}$`. Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md).

| Modello | Significato                             |
|---------|-------------------------------------|
| `^`     | corrisponde all'inizio della stringa |
| `\d{3}` | corrisponde esattamente a 3 caratteri numerici  |
| `-`     | corrisponde al carattere '-'           |
| `\d{3}` | corrisponde esattamente a 3 caratteri numerici  |
| `-`     | corrisponde al carattere '-'           |
| `\d{4}` | corrisponde esattamente a 4 caratteri numerici  |
| `$`     | corrisponde alla fine della stringa       |

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet4":::

Questo singolo criterio di ricerca corrisponde a molte stringhe valide. Le espressioni regolari sono preferibili per eseguire ricerche o convalide in base a un modello, anziché a una singola stringa di testo.

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../programming-guide/index.md)
- [Stringhe](../programming-guide/strings/index.md)
- [LINQ e stringhe](../programming-guide/concepts/linq/linq-and-strings.md)
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>
- [.NET Framework espressioni regolari](../../standard/base-types/regular-expressions.md)
- [Linguaggio di espressioni regolari-riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md)
- [Procedure consigliate per l'uso delle stringhe in .NET](../../standard/base-types/best-practices-strings.md)
