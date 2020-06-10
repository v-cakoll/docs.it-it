---
title: Come concatenare più stringhe (Guida a C#)
description: Esistono diversi modi per concatenare le stringhe in C#. Di seguito sono descritte le opzioni e le motivazioni delle diverse scelte.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: ef3d79c5b40d08cb76e58eba1c8831c468fd1fc0
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84663018"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a>Come concatenare più stringhe (Guida a C#)

La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa. Le stringhe vengono concatenate usando l'operatore `+`. Per i valori letterali e le costanti di stringa, la concatenazione viene eseguita in fase di compilazione; non viene eseguita alcuna concatenazione in fase di esecuzione. Per le variabili di stringa, la concatenazione viene eseguita solo in fase di esecuzione.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

L'esempio seguente usa la concatenazione per suddividere un valore letterale di stringa lungo in stringhe più piccole per migliorare la leggibilità nel codice sorgente. Queste parti sono concatenate in una singola stringa in fase di compilazione. Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet1":::

Per concatenare le variabili di stringa, è possibile usare gli `+` `+=` operatori o, l' [interpolazione di stringhe](../language-reference/tokens/interpolated.md) o i <xref:System.String.Format%2A?displayProperty=nameWithType> metodi, <xref:System.String.Concat%2A?displayProperty=nameWithType> <xref:System.String.Join%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> . L'operatore `+` è facile da usare e rende il codice intuitivo. Anche se si usano diversi operatori `+` in un'unica istruzione, il contenuto della stringa viene copiato una sola volta. Il codice seguente mostra esempi dell'uso degli operatori `+` e `+=` per concatenare le stringhe:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet2":::

In alcune espressioni risulta più semplice concatenare le stringhe usando l'interpolazione di stringhe, come illustrato nel codice seguente:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet3":::

> [!NOTE]
> Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota.

Un altro metodo per concatenare le stringhe è <xref:System.String.Format%2A?displayProperty=nameWithType>. Questo metodo è utile quando si compila una stringa da un numero ridotto di stringhe dei componenti.

In altri casi, è possibile combinare le stringhe in un ciclo in cui non si conosce il numero di stringhe di origine combinate e il numero effettivo di stringhe di origine può essere di grandi dimensioni. La classe <xref:System.Text.StringBuilder> è stata progettata per questi scenari. Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet4":::

Per altre informazioni sui [motivi per scegliere la concatenazione di stringhe o la `StringBuilder` classe](https://docs.microsoft.com/dotnet/api/system.text.stringbuilder#the-string-and-stringbuilder-types), vedere.

Un'altra opzione per unire le stringhe di una raccolta consiste nell'usare il metodo <xref:System.String.Concat%2A?displayProperty=nameWithType>. Usare <xref:System.String.Join%2A?displayProperty=nameWithType> il metodo se le stringhe di origine devono essere separate da un delimitatore. Il codice seguente combina una matrice di parole con entrambi i metodi:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet5":::

Infine, è possibile usare [LINQ](../programming-guide/concepts/linq/index.md) e il metodo <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> per unire le stringhe di una raccolta. Questo metodo combina le stringhe di origine usando un'espressione lambda. L'espressione lambda esegue le operazioni necessarie per aggiungere ogni stringa all'accumulo esistente. L'esempio seguente combina una matrice di parole aggiungendo uno spazio tra ogni parola nella matrice:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet6":::

## <a name="see-also"></a>Vedere anche

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [Guida per programmatori C#](../programming-guide/index.md)
- [Stringhe](../programming-guide/strings/index.md)
