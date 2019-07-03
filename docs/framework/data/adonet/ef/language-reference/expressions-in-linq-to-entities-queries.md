---
title: Espressioni in query di LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 0b77fc4c2a7c7df6efc9f4d8ce4001c39250ab94
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539906"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Espressioni in query di LINQ to Entities
Un'espressione è un frammento di codice che può restituire un singolo valore, oggetto, metodo o spazio dei nomi. Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un nome semplice, ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo. Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi. Le espressioni possono pertanto essere da semplici a molto complesse.  
  
 Nelle query LINQ to Entities, le espressioni possono contenere qualsiasi elemento consentito dai tipi all'interno di <xref:System.Linq.Expressions> dello spazio dei nomi, tra cui espressioni lambda. Le espressioni che possono essere usate in LINQ alle query di entità sono un superset delle espressioni che può essere usato per eseguire query di [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Le espressioni che fanno parte di query sul [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono limitate a operazioni supportate dal `ObjectQuery<T>` e l'origine dati sottostante.  
  
 Nell'esempio seguente il confronto nella clausola `Where` è un'espressione:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Costrutti di linguaggio specifici, ad esempio C# `unchecked`, non hanno significato in LINQ to Entities.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Espressioni costanti](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Espressioni di confronto](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Confronti Null](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Espressioni di inizializzazione](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Le relazioni, le proprietà di navigazione e le chiavi esterne](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
