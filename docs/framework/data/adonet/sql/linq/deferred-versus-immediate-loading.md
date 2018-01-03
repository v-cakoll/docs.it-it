---
title: Caricamento posticipato e immediato
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 992d9a018f81bbd3f0c9204168f513024769e079
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="deferred-versus-immediate-loading"></a>Caricamento posticipato e immediato
Quando si esegue una query per un oggetto, si recupera in effetti solo l'oggetto richiesto. Il *correlati* oggetti non vengono recuperati contemporaneamente. (Per ulteriori informazioni, vedere [l'esecuzione di query tra relazioni](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Non è possibile verificare che gli oggetti correlati non siano già stati caricati, perché un tentativo di accedervi produce una richiesta che ne comporta il recupero.  
  
 Ad esempio, è possibile eseguire una query per un particolare set di ordini, quindi inviare saltuariamente un avviso tramite posta elettronica a clienti particolari. Inizialmente potrebbe non essere necessario recuperare tutti i dati del cliente con ogni ordine. In questo caso è possibile usare il caricamento posticipato per rinviare il recupero di informazioni aggiuntive finché non sarà assolutamente necessario. Si consideri l'esempio seguente:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Potrebbe anche essere vero il contrario. Si dispone di un'applicazione che richiede la visualizzazione contemporanea dei dati dei clienti e degli ordini. È noto che sono necessari entrambi i set di dati e che l'applicazione richiede informazioni sugli ordini per ogni cliente non appena vengono restituiti i risultati. Non si desidera inviare singole query per gli ordini di ogni cliente, bensì recuperare i dati degli ordini insieme ai clienti.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 È inoltre possibile creare un join tra clienti e ordini in una query definendo il prodotto incrociato e recuperando tutti i relativi bit di dati come un'unica grande proiezione. Tali risultati non sono tuttavia entità. (Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). Le entità sono oggetti con un'identità che è possibile modificare, mentre i risultati in questione sono proiezioni che non possono essere modificate né salvate in modo permanente. È inoltre possibile che vengano recuperati molti dati ridondanti, in quanto ogni cliente viene ripetuto per ogni ordine nell'output del join bidimensionale.  
  
 È invece utile disporre di un modo per recuperare contemporaneamente un set di oggetti correlati. Il set è una sezione delineata di un grafico che consente di recuperare sempre solo la quantità di dati necessaria per l'uso desiderato. A tale scopo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce <xref:System.Data.Linq.DataLoadOptions> per il caricamento immediato di un'area del modello a oggetti. I metodi comprendono:  
  
-   Il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per caricare immediatamente dati relativi alla destinazione principale.  
  
-   Il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> per filtrare gli oggetti recuperati per una determinata relazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
