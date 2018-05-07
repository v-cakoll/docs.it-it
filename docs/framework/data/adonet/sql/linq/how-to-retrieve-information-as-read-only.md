---
title: 'Procedura: recuperare informazioni in sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: dd3a510339bca8649f5654d00a9cbdfba156d92c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-information-as-read-only"></a>Procedura: recuperare informazioni in sola lettura
Quando non si prevede di modificare i dati, è possibile migliorare le prestazione delle query effettuando la ricerca di risultati di sola lettura.  
  
 Per implementare l'elaborazione di sola lettura, impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su `false`.  
  
> [!NOTE]
>  Quando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> è impostato su `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> viene impostato in modo implicito su `false`.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene recuperato una raccolta di date di assunzione dei dipendenti di sola lettura.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [Caricamento posticipato e immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
