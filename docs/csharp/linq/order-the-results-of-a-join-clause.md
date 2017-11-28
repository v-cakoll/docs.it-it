---
title: Ordinare i risultati di una clausola join
description: Come ordinare i risultati di una clausola join.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a>Ordinare i risultati di una clausola join
Questo esempio descrive come ordinare i risultati di un'operazione di join. Si noti che l'ordinamento viene eseguito dopo l'operazione di join. In genere, sebbene sia possibile, non è consigliabile usare una clausola `orderby` con una o più sequenze di origine prima dell'operazione di join. Alcuni provider LINQ potrebbero non mantenere tale ordinamento dopo l'operazione di join.  
  
## <a name="example"></a>Esempio  
 Questa query crea un join di gruppo e quindi ordina i gruppi in base all'elemento categoria che è ancora nell'ambito. Nell'inizializzatore di tipi anonimi una sottoquery ordina tutti gli elementi corrispondenti della sequenza di prodotti.  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>Vedere anche  
 [Espressioni di query LINQ](index.md)  
 [Clausola orderby](../language-reference/keywords/orderby-clause.md)  
 [Clausola join](../language-reference/keywords/join-clause.md) 
