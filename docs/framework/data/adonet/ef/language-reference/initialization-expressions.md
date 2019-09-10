---
title: Espressioni di inizializzazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 5d6656ab77f7ad0f7366a230d98b95cff5b2677b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854440"
---
# <a name="initialization-expressions"></a>Espressioni di inizializzazione
Un'espressione di inizializzazione consente di inizializzare un nuovo oggetto. La maggior parte delle espressioni di inizializzazione è supportata, incluse le più recenti espressioni di inizializzazione di C# 3.0 e Visual Basic 9.0. I tipi seguenti possono essere inizializzati e restituiti da una query LINQ to Entities:  
  
- Raccolta di zero o più oggetti entità tipizzate o proiezione di tipi complessi definiti nel modello concettuale.  
  
- Tipi CLR supportati dal Entity Framework.
  
- Raccolte inline.  
  
- Tipi anonimi.  
  
 L'inizializzazione dei tipi anonimi è illustrata nell'esempio seguente nella sintassi delle espressioni di query:  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata l'inizializzazione di un tipo anonimo:  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 È inoltre supportata l'inizializzazione delle classi definite dall'utente. Il modello di inizializzazione di C# 3.0 e Visual Basic 9.0 è supportato e presuppone che i metodi Get e Set della proprietà siano simmetrici. Nell'esempio seguente nella sintassi delle espressioni di query viene illustrata l'inizializzazione di una classe personalizzata nella query:  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata l'inizializzazione di una classe personalizzata nella query:  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni in query di LINQ to Entities](expressions-in-linq-to-entities-queries.md)
