---
title: Espressioni in query di LINQ to Entities
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
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d8bfeaa3eb96e69fdf3b10d132ea1e0266d56c78
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="expressions-in-linq-to-entities-queries"></a>Espressioni in query di LINQ to Entities
Un'espressione è un frammento di codice che può restituire un singolo valore, oggetto, metodo o spazio dei nomi. Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un nome semplice, ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo. Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi. Le espressioni possono pertanto essere da semplici a molto complesse.  
  
 In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query, le espressioni possono contenere qualsiasi elemento consentito dai tipi all'interno di <xref:System.Linq.Expressions> dello spazio dei nomi, tra cui espressioni lambda. Le espressioni che possono essere usate nelle query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sono un superset delle espressioni che possono essere usate per eseguire query su [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Le espressioni che fanno parte di query su di [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono limitate a operazioni supportate da `ObjectQuery<T>` e l'origine dati sottostante.  
  
 Nell'esempio seguente il confronto nella clausola `Where` è un'espressione:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  I costrutti di linguaggio specifici, ad esempio `unchecked` C#, non hanno significato in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## <a name="in-this-section"></a>In questa sezione  
 [Espressioni costanti](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Espressioni di confronto](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Confronti Null](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Espressioni di inizializzazione](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Proprietà di navigazione](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
