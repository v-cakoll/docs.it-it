---
title: Come convertire una stringa in una guida per la C# programmazione di numeri
ms.date: 02/11/2019
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 21732acd65eb4522b19ce84600fd8b333fb8a705
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711870"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Come convertire una stringa in un numero (C# guida per programmatori)

È possibile convertire una [stringa](../../language-reference/builtin-types/reference-types.md) in un numero chiamando il metodo `Parse` o `TryParse` disponibile per i vari tipi numerici (`int`, `long`, `double` e così via) oppure usando i metodi nella classe <xref:System.Convert?displayProperty=nameWithType>.  
  
 Se si ha una stringa, è leggermente più efficiente e semplice chiamare un metodo `TryParse` (ad esempio, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) o un metodo `Parse` (ad esempio, [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)).  L'uso di un metodo <xref:System.Convert> è più utile per gli oggetti generali che implementano <xref:System.IConvertible>.  
  
 È possibile usare i metodi `Parse` o `TryParse` sul tipo numerico che si prevede sia contenuto nella stringa, ad esempio il tipo <xref:System.Int32?displayProperty=nameWithType>.  Il metodo <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> utilizza il metodo <xref:System.Int32.Parse%2A> internamente.  Il metodo `Parse` restituisce il numero convertito. Il metodo `TryParse` restituisce un valore <xref:System.Boolean> che indica se la conversione ha avuto esito positivo e restituisce il numero convertito in un [parametro `out`](../../language-reference/keywords/out.md). Se il formato della stringa non è valido, `Parse` genera un'eccezione, mentre `TryParse` restituisce `false`. Quando si chiama un metodo `Parse`, è sempre consigliabile usare la gestione delle eccezioni per intercettare <xref:System.FormatException> in caso di esito negativo dell'operazione di analisi.  
  
## <a name="calling-the-parse-and-tryparse-methods"></a>Chiamata dei metodi Parse e TryParse

I metodi `Parse` e `TryParse` ignorano lo spazio vuoto all'inizio e alla fine della stringa, ma tutti gli altri devono essere caratteri che costituiscono il tipo numerico appropriato (`int`, `long`, `ulong`, `float`, `decimal` e così via).  Gli spazi vuoti all'interno della stringa che sostituisce il numero generano un errore.  Ad esempio, è possibile usare `decimal.TryParse` per analizzare "10", "10,3" o "  10  ", ma non è possibile usare questo metodo per ottenere 10 da "10X", "1 0" (si noti lo spazio interno), "10 ,3" (si noti lo spazio interno), "10e1" (in questo caso `float.TryParse` funziona) e così via. Inoltre, una stringa con valore `null` o <xref:System.String.Empty?displayProperty=nameWithType> non viene analizzata correttamente. È possibile cercare una stringa vuota o Null prima di tentare di analizzarla chiamando il metodo <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>. 

L'esempio seguente illustra le chiamate con esito positivo e negativo per `Parse` e `TryParse`.  
  
[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]  

Nell'esempio seguente viene illustrato un approccio per l'analisi di una stringa che è previsto includa caratteri numerici iniziali (inclusi caratteri esadecimali) e caratteri non numerici finali. I caratteri validi dall'inizio di una stringa vengono assegnati a una nuova stringa prima di chiamare il metodo <xref:System.Int32.TryParse%2A>. Dato che le stringhe da analizzare contengono un numero ridotto di caratteri, nell'esempio viene chiamato il metodo <xref:System.String.Concat%2A?displayProperty=nameWithType> per assegnare i caratteri validi a una nuova stringa. Per una stringa più grande, è invece possibile usare la classe <xref:System.Text.StringBuilder>. 
  
[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]  

## <a name="calling-the-convert-methods"></a>Chiamata dei metodi Convert

Nella tabella seguente sono elencati alcuni dei metodi della classe <xref:System.Convert> che è possibile usare per convertire una stringa in numero.  
  
|Tipo numerico|Metodo|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 Nell'esempio seguente viene chiamato il metodo <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> per convertire una stringa di input in un valore [int](../../language-reference/builtin-types/integral-numeric-types.md). L'esempio rileva le due eccezioni più comuni che possono essere generate da questo metodo, <xref:System.FormatException> e <xref:System.OverflowException>. Se il numero risultante può essere incrementato senza superare <xref:System.Int32.MaxValue?displayProperty=nameWithType>, l'esempio aggiunge 1 al risultato e visualizza l'output.  
  
[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi](./index.md)
- [Come determinare se una stringa rappresenta un valore numerico](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [Esempio: Utilità di formattazione di .NET Core WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
