---
title: Espressioni costanti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 616f297c261c4309dc0db7a4efe2fcad8cc00966
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762517"
---
# <a name="constant-expressions"></a>Espressioni costanti
Un'espressione costante è costituita da un valore costante. I valori costanti vengono convertiti direttamente in espressioni costanti dell'albero dei comandi, senza conversione nel client. Questo vale anche per le espressioni che hanno come risultato un valore costante. È pertanto possibile prevedere il comportamento dell'origine dati per tutte le espressioni che contengono costanti. Il comportamento risultante può essere diverso da quello in CLR.  
  
 Nell'esempio seguente è illustrata un'espressione costante valutata nel server.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] non supporta l'uso di una classe utente come costante. Un riferimento a una proprietà in una classe utente è tuttavia considerato una costante e viene convertito in un'espressione costante dell'albero dei comandi ed eseguito nell'origine dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni in query di LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
