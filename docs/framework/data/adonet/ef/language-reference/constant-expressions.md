---
title: Espressioni costanti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 10c74ede8d490bf96a9d0855889669bdc2628b01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209203"
---
# <a name="constant-expressions"></a>Espressioni costanti
Un'espressione costante è costituita da un valore costante. I valori costanti vengono convertiti direttamente in espressioni costanti dell'albero dei comandi, senza conversione nel client. Questo vale anche per le espressioni che hanno come risultato un valore costante. È pertanto possibile prevedere il comportamento dell'origine dati per tutte le espressioni che contengono costanti. Il comportamento risultante può essere diverso da quello in CLR.  
  
 Nell'esempio seguente è illustrata un'espressione costante valutata nel server.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] non supporta l'utilizzo di una classe utente come costante. Un riferimento a una proprietà in una classe utente è tuttavia considerato una costante e viene convertito in un'espressione costante dell'albero dei comandi ed eseguito nell'origine dati.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni in query di LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
