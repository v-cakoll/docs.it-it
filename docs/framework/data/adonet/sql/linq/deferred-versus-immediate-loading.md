---
title: Caricamento posticipato e immediato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
ms.openlocfilehash: ae20dbe557c3cf56a273556c24578056843e9af6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096992"
---
# <a name="deferred-versus-immediate-loading"></a>Caricamento posticipato e immediato
Quando si esegue una query per un oggetto, si recupera in effetti solo l'oggetto richiesto. Il *correlati* oggetti non vengono recuperati contemporaneamente. (Per altre informazioni, vedere [eseguire query tra relazioni](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Non è possibile verificare che gli oggetti correlati non siano già stati caricati, perché un tentativo di accedervi produce una richiesta che ne comporta il recupero.  
  
 Ad esempio, è possibile eseguire una query per un particolare set di ordini e quindi inviare saltuariamente una notifica tramite posta elettronica a clienti particolari. Inizialmente potrebbe non essere necessario recuperare tutti i dati del cliente con ogni ordine. In questo caso è possibile usare il caricamento posticipato per rinviare il recupero di informazioni aggiuntive finché non sarà assolutamente necessario. Si consideri l'esempio seguente:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Potrebbe anche essere vero il contrario. Si dispone di un'applicazione che richiede la visualizzazione contemporanea dei dati dei clienti e degli ordini. È noto che sono necessari entrambi i set di dati e che l'applicazione richiede informazioni sugli ordini per ogni cliente non appena vengono restituiti i risultati. Non si desidera inviare singole query per gli ordini di ogni cliente, bensì recuperare i dati degli ordini insieme ai clienti.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 È inoltre possibile creare un join tra clienti e ordini in una query definendo il prodotto incrociato e recuperando tutti i relativi bit di dati come un'unica grande proiezione. Tali risultati non sono tuttavia entità. (Per altre informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). Le entità sono oggetti con un'identità che è possibile modificare, mentre i risultati in questione sono proiezioni che non possono essere modificate né salvate in modo permanente. È inoltre possibile che vengano recuperati molti dati ridondanti, in quanto ogni cliente viene ripetuto per ogni ordine nell'output del join bidimensionale.  
  
 È invece utile disporre di un modo per recuperare contemporaneamente un set di oggetti correlati. Il set è una sezione delineata di un grafico che consente di recuperare sempre solo la quantità di dati necessaria per l'uso desiderato. A tale scopo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce <xref:System.Data.Linq.DataLoadOptions> il caricamento immediato di un'area del modello a oggetti. I metodi comprendono:  
  
-   Il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per caricare immediatamente dati relativi alla destinazione principale.  
  
-   Il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> per filtrare gli oggetti recuperati per una determinata relazione.  
  
## <a name="see-also"></a>Vedere anche

- [Concetti relatici alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
