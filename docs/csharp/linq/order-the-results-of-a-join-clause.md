---
title: Ordinare i risultati di una clausola join (LINQ in C#)
description: Informazioni su come ordinare i risultati di una clausola join LINQ in C#.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659865"
---
# <a name="order-the-results-of-a-join-clause"></a>Ordinare i risultati di una clausola join

Questo esempio descrive come ordinare i risultati di un'operazione di join. Si noti che l'ordinamento viene eseguito dopo l'operazione di join. In genere, sebbene sia possibile, non è consigliabile usare una clausola `orderby` con una o più sequenze di origine prima dell'operazione di join. Alcuni provider LINQ potrebbero non mantenere tale ordinamento dopo l'operazione di join.

## <a name="example"></a>Esempio

Questa query crea un join di gruppo e quindi ordina i gruppi in base all'elemento categoria che è ancora nell'ambito. Nell'inizializzatore di tipi anonimi una sottoquery ordina tutti gli elementi corrispondenti della sequenza di prodotti.

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
- [Clausola orderby](../language-reference/keywords/orderby-clause.md)
- [clausola join](../language-reference/keywords/join-clause.md)
