---
title: Scrivere query LINQ in C#
description: Informazioni su come scrivere query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: ed32543b0422e0664a8577f2c27f7c7c00a719a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "65632887"
---
# <a name="write-linq-queries-in-c"></a>Scrivere query LINQ in C\#

Questo articolo illustra i tre modi in cui è possibile scrivere una query LINQ in C#:

1. Usare la sintassi di query.

2. Usare la sintassi di metodo.

3. Usare una combinazione di sintassi di query e sintassi di metodo.

Gli esempi seguenti illustrano alcune semplici query LINQ usando ogni approccio indicato sopra. In generale, la regola è usare (1) ogni volta che è possibile e usare (2) e (3) ogni volta che è necessario.

> [!NOTE]
> Queste query operano su raccolte in memoria semplici, tuttavia, la sintassi di base è identica a quella usata in LINQ to Entities e LINQ to XML.

## <a name="example---query-syntax"></a>Esempio - Sintassi di query

Il metodo consigliato per scrivere la maggior parte delle query è usare la *sintassi di query* per creare *espressioni di query*. Nell'esempio seguente sono riportate tre espressioni di query. La prima espressione di query dimostra in che modo si filtrano o si limitano i risultati applicando le condizioni con una clausola `where`. Restituisce tutti gli elementi nella sequenza di origine i cui valori sono maggiori di 7 o minori di 3. La seconda espressione illustra come ordinare i risultati restituiti. La terza espressione illustra come raggruppare i risultati in base a una chiave. Questa query restituisce due gruppi in base alla prima lettera della parola.

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

Si noti che il tipo delle query è <xref:System.Collections.Generic.IEnumerable%601>. Tutte queste query potrebbero essere scritte usando `var` come indicato nell'esempio seguente:

`var query = from num in numbers...`

In ognuno degli esempi precedenti le query non vengono effettivamente eseguite finché non si esegue l'iterazione della variabile di query in un'istruzione `foreach` o un'altra istruzione. Per ulteriori informazioni, vedere [Introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="example---method-syntax"></a>Esempio - Sintassi del metodo

Alcune operazioni di query devono essere espresse come una chiamata al metodo. I più comuni di tali metodi sono quelli che restituiscono valori numerici singleton, ad esempio <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> e così via. Questi metodi devono sempre essere chiamati per ultimi in una query poiché rappresentano solo un singolo valore e non possono essere usati come origine per un'operazione di query aggiuntiva. Nell'esempio seguente viene illustrata una chiamata al metodo in un'espressione di query:

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

Se il metodo usa i parametri Action o Func, questi vengono specificati sotto forma di espressione [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md), come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

Nelle query precedenti solo la query n. 4 viene immediatamente eseguita. Ciò è dovuto al fatto che viene restituito un valore singolo invece di una raccolta <xref:System.Collections.Generic.IEnumerable%601> generica. Il metodo stesso deve usare `foreach` per calcolare il proprio valore.

Ognuna delle query precedenti può essere scritta usando la tipizzazione implicita con [var](../language-reference/keywords/var.md), come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a>Esempio - Sintassi di query e di metodo mista

In questo esempio viene illustrato come usare la sintassi di metodo per i risultati di una clausola di query. È sufficiente racchiudere l'espressione di query tra parentesi e quindi applicare l'operatore punto e chiamare il metodo. Nell'esempio seguente la query n. 7 restituisce un conteggio dei numeri il cui valore è compreso tra 3 e 7. In generale, tuttavia, è preferibile usare una seconda variabile per archiviare il risultato della chiamata al metodo. In questo modo è meno probabile che si crei confusione con i risultati della query.

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

Poiché la query n. 7 restituisce un singolo valore e non una raccolta, la query viene eseguita immediatamente.

La query precedente può essere scritta usando la tipizzazione implicita con `var`, come segue:

```csharp
var numCount = (from num in numbers...
```

Può essere scritta nella sintassi di metodo come indicato di seguito:

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

Può essere scritta usando la tipizzazione esplicita, come indicato di seguito:

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: scrittura di query in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [Language Integrated Query (LINQ)](index.md)
- [clausola where](../language-reference/keywords/where-clause.md)
