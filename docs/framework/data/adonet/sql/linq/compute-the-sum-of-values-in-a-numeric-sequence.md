---
title: Calcolare la somma dei valori in una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3a404068c2d89610aa9b01b392bca40f82e17707
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247920"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Calcolare la somma dei valori in una sequenza numerica
Per calcolare la somma di valori numerici in una sequenza, usare l'operatore <xref:System.Linq.Enumerable.Sum%2A>.  
  
 Di seguito sono riportate le caratteristiche dell'operatore `Sum` in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
- L'operatore di aggregazione `Sum` dell'operatore di query standard restituisce valori zero per tutte le sequenze vuote o che contengono solo valori null. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la semantica di SQL rimane invariata. Per questo motivo `Sum` restituisce null anziché zero per una sequenza vuota o per una sequenza che contiene solo valori null.  
  
- Le limitazioni di SQL sui risultati intermedi vengono applicate agli aggregati in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. La somma delle quantità Integer a 32 bit non viene calcolata usando risultati a 64 bit e l'overflow può verificarsi per la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] conversione di `Sum`. Questa possibilità esiste anche se l'implementazione dell'operatore di query standard non provoca un overflow per la corrispondente sequenza in memoria.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato il costo di trasporto complessivo di tutti gli ordini contenuti nella tabella `Order`.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `64942.6900`.  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato il numero complessivo di unità ordinate per tutti i prodotti.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `780`.  
  
 Notare che è necessario eseguire il cast dei tipi `short`, ad esempio `UnitsOnOrder`, in quanto in `Sum` non è disponibile alcun overload per tali tipi.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>Vedere anche

- [Query di aggregazione](aggregate-queries.md)
- [Download di database di esempio](downloading-sample-databases.md)
