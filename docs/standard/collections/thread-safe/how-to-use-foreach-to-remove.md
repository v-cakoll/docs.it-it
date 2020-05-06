---
title: Usare foreach per rimuovere elementi in un oggetto BlockingCollection
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: 1255fcda89396ea8ff9abf6cf111e6dd9ea5a87d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82861005"
---
# <a name="use-foreach-to-remove-items-in-a-blockingcollection"></a>Usare foreach per rimuovere elementi in un oggetto BlockingCollection

Oltre a raccogliere elementi da un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> il metodo e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> , è possibile usare anche [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) con <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> per rimuovere gli elementi fino a quando non viene completata l'aggiunta e la raccolta è vuota. Questa operazione viene definita *enumerazione mutante* o *enumerazione di consumo* perché, a differenza di un ciclo `foreach` tipico (`For Each`), questo enumeratore modifica la raccolta di origine rimuovendo elementi.

## <a name="example"></a>Esempio

L'esempio seguente illustra come rimuovere tutti gli elementi di un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando un ciclo `foreach` (`For Each`).

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

Questo esempio usa un ciclo `foreach` con il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> nel thread di consumo, che rimuove ogni elemento dalla raccolta mentre viene enumerato. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limita il numero massimo di elementi presenti nella raccolta in qualsiasi momento. Tale enumerazione della raccolta blocca il thread consumer se non sono disponibili elementi o se la raccolta è vuota. In questo esempio il blocco non rappresenta un problema perché il thread producer aggiunge elementi più velocemente di quanto possano essere usati.

Restituisce <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> un oggetto `IEnumerable<T>`, pertanto l'ordine non può essere garantito. Tuttavia, internamente <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> un viene usato come tipo di raccolta sottostante, che consente di rimuovere dalla coda gli oggetti dopo l'ordinamento First-in-First-out (FIFO). Se le chiamate simultanee a <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> vengono effettuate, saranno competitive. Un elemento utilizzato (rimosso dalla coda) in un'enumerazione non può essere osservato nell'altro.

Per enumerare la raccolta senza modificarla, usare `foreach` (`For Each`) senza il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Tuttavia, è importante tenere presente che questo tipo di enumerazione rappresenta uno snapshot della raccolta in un momento preciso. Se altri thread aggiungono o rimuovono elementi contemporaneamente mentre si esegue il ciclo, il ciclo potrebbe non rappresentare lo stato effettivo della raccolta.

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Programmazione parallela](../../../../docs/standard/parallel-programming/index.md)
