---
title: Ordinare i risultati di una clausola join
description: Come ordinare i risultati di una clausola join.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f426152e614ed9a9c4aa41d7ba7cb8ddf1cd3063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269700"
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
