---
title: Espressioni di inizializzazione
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
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dd5706c2eb09b0161d7eb1a4412471e9e75fcf75
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="initialization-expressions"></a>Espressioni di inizializzazione
Un'espressione di inizializzazione consente di inizializzare un nuovo oggetto. La maggior parte delle espressioni di inizializzazione è supportata, incluse le più recenti espressioni di inizializzazione di C# 3.0 e Visual Basic 9.0. I tipi seguenti possono essere inizializzati e restituiti da una query LINQ to Entities:  
  
-   Raccolta di zero o più oggetti entità tipizzate o proiezione di tipi complessi definiti nel modello concettuale.  
  
-   Tipi CLR supportati da [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  
  
-   Raccolte inline.  
  
-   Tipi anonimi.  
  
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
 [Espressioni di query LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
