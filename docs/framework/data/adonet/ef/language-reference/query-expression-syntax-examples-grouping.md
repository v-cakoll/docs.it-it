---
title: 'Esempi di sintassi delle espressioni di query: Raggruppamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: bbb41918e4d3637ff1e04275ad6151510dfa036b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249496"
---
# <a name="query-expression-syntax-examples-grouping"></a>Esempi di sintassi delle espressioni di query: Raggruppamento
Negli esempi di questo argomento viene illustrato come utilizzare il `GroupBy` metodo per eseguire una query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando la sintassi delle espressioni di query. Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono restituiti oggetti `Address` raggruppati in base al codice postale. I risultati vengono proiettati in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono restituiti oggetti `Contact` raggruppati in base alla prima lettera del cognome del contatto. I risultati sono anche ordinati in base alla prima lettera del cognome e proiettati in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono restituiti oggetti `SalesOrderHeader` raggruppati in base all'ID cliente. Viene restituito anche il numero di vendite per ogni cliente.  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a>Vedere anche

- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
