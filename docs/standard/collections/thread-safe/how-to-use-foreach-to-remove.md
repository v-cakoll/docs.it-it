---
title: 'Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: f9a858dea74be63634f887c4204aefa8ac338ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711233"
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection

Oltre a estrarre elementi da un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, è anche possibile usare [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) per rimuovere gli elementi finché l'aggiunta viene completata e la raccolta è vuota. Questa operazione viene definita *enumerazione mutante* o *enumerazione di consumo* perché, a differenza di un ciclo `foreach` tipico (`For Each`), questo enumeratore modifica la raccolta di origine rimuovendo elementi.

## <a name="example"></a>Esempio

L'esempio seguente illustra come rimuovere tutti gli elementi di un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando un ciclo `foreach` (`For Each`).

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

Questo esempio usa un ciclo `foreach` con il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> nel thread di consumo, che rimuove ogni elemento dalla raccolta mentre viene enumerato. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limita il numero massimo di elementi presenti nella raccolta in qualsiasi momento. Tale enumerazione della raccolta blocca il thread consumer se non sono disponibili elementi o se la raccolta è vuota. In questo esempio il blocco non rappresenta un problema perché il thread producer aggiunge elementi più velocemente di quanto possano essere usati.

Non esiste alcuna garanzia che gli elementi vengano enumerati nello stesso ordine in cui sono stati aggiunti dai thread producer.

Per enumerare la raccolta senza modificarla, usare `foreach` (`For Each`) senza il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Tuttavia, è importante tenere presente che questo tipo di enumerazione rappresenta uno snapshot della raccolta in un momento preciso. Se altri thread aggiungono o rimuovono elementi contemporaneamente mentre si esegue il ciclo, il ciclo potrebbe non rappresentare lo stato effettivo della raccolta.

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Programmazione parallela](../../../../docs/standard/parallel-programming/index.md)
