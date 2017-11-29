---
title: Gestire i valori Null nelle espressioni di query
description: Come gestire i valori Null nelle espressioni di query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: d16256e31b073a599504ffef6501ed34430a7694
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="handle-null-values-in-query-expressions"></a>Gestire i valori Null nelle espressioni di query

In questo esempio viene illustrato come gestire i possibili valori Null nelle raccolte di origine. Una raccolta di oggetti, ad esempio <xref:System.Collections.Generic.IEnumerable%601>, può contenere elementi il cui valore è [Null](../language-reference/keywords/null.md). Se una raccolta di origine è Null o contiene un elemento il cui valore è Null e la query non gestisce valori Null, verrà generata un'eccezione <xref:System.NullReferenceException> quando si esegue la query.  
  
## <a name="example"></a>Esempio

 È possibile codificare in modo sicuro per evitare un'eccezione di riferimento Null come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 Nell'esempio precedente la clausola `where` esclude tutti gli elementi Null nella sequenza di categorie. Questa tecnica è indipendente dal controllo Null nella clausola join. In questo esempio è possibile usare l'espressione condizionale con Null poiché `Products.CategoryID` è di tipo `int?`, vale a dire una sintassi abbreviata di `Nullable<int>`.  
  
## <a name="example"></a>Esempio

 Se in una clausola join solo una delle chiavi di confronto è un tipo di valore nullable, è possibile eseguire il cast delle altre chiavi a un tipo nullable nell'espressione di query. Nell'esempio seguente si supponga che `EmployeeID` sia una colonna contenente valori di tipo `int?`:  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Nullable%601>  
 [Espressioni di query LINQ](index.md)  
 [Tipi nullable](../programming-guide/nullable-types/index.md)
