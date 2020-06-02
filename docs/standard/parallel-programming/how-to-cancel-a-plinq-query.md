---
title: 'Procedura: Annullare una query PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 09405a8a9f5d96d80454bcc98cbf29db54df6725
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288212"
---
# <a name="how-to-cancel-a-plinq-query"></a>Procedura: Annullare una query PLINQ
Gli esempi seguenti descrivono due modi per annullare una query PLINQ. Il primo esempio descrive come annullare una query costituita principalmente da attraversamento di dati. Il secondo esempio descrive come annullare una query che contiene una funzione utente onerosa dal punto di vista delle risorse di calcolo.

> [!NOTE]
> Quando è abilitato "Just My Code", Visual Studio si interrompe in corrispondenza della riga che genera l'eccezione e visualizza un messaggio di errore che indica che l'eccezione non è stata gestita dal codice utente. Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.
>
> Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).

## <a name="example"></a>Esempio

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

Il framework PLINQ non gestisce un singolo oggetto <xref:System.OperationCanceledException> in un oggetto <xref:System.AggregateException?displayProperty=nameWithType>. L'oggetto <xref:System.OperationCanceledException> deve essere gestito in un blocco catch separato. Se uno o più delegati dell'utente generano un oggetto OperationCanceledException (externalCT), usando un oggetto <xref:System.Threading.CancellationToken?displayProperty=nameWithType> esterno, ma senza altre eccezioni e se la query è stata definita come `AsParallel().WithCancellation(externalCT)`, PLINQ genererà un singolo oggetto <xref:System.OperationCanceledException>(externalCT) anziché un oggetto <xref:System.AggregateException?displayProperty=nameWithType>. Tuttavia, se un delegato dell'utente genera un oggetto <xref:System.OperationCanceledException> e un altro delegato genera un altro tipo di eccezione, entrambe le eccezioni vengono gestite in un oggetto <xref:System.AggregateException>.

Le indicazioni generali sull'annullamento sono le seguenti:

1. Se si esegue l'annullamento delegata dall'utente, è necessario informare PLINQ sull'esterno <xref:System.Threading.CancellationToken> e generare un <xref:System.OperationCanceledException> (externalCT).

2. Se si verifica l'annullamento e non vengono generate altre eccezioni, gestire un oggetto <xref:System.OperationCanceledException> anziché un oggetto <xref:System.AggregateException> .

## <a name="example"></a>Esempio

L'esempio seguente mostra come gestire l'annullamento in presenza di una funzione onerosa dal punto di vista delle risorse di calcolo nel codice utente.

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

Quando si gestisce l'annullamento nel codice utente, non è necessario usare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nella definizione di query. Tuttavia, si consiglia di utilizzare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> , poiché <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> non ha effetto sulle prestazioni delle query e consente di gestire l'annullamento dagli operatori di query e dal codice utente.

Per garantire velocità di risposta del sistema, è consigliabile verificare l'annullamento circa una volta al millisecondo, ma è considerato accettabile qualsiasi periodo fino a 10 millisecondi. Questa frequenza non dovrebbe avere impatto negativo sulle prestazioni del codice.

Quando un enumeratore viene eliminato, ad esempio quando il codice si interrompe da un ciclo foreach (for each in Visual Basic) che esegue l'iterazione sui risultati della query, la query viene annullata, ma non viene generata alcuna eccezione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
- [Annullamento in thread gestiti](../threading/cancellation-in-managed-threads.md)
