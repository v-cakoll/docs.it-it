---
title: Eseguire una sottoquery su un'operazione di raggruppamento (LINQ in C#)
description: Come eseguire una sottoquery su un'operazione di raggruppamento usando LINQ in C#.
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: fd26f87ad7d5b4892f086bf8c7a34cf19a7f9e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173367"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Eseguire una sottoquery su un'operazione di raggruppamento

Questo articolo descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo. La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`. La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna. Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.  
  
Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).  
  
Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md). L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.  
  
## <a name="example"></a>Esempio

> [!NOTE]
> Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]

La query nel frammento di codice precedente può essere scritta anche usando la sintassi del metodo. Il frammento di codice seguente è una query semanticamente equivalente scritta usando la sintassi del metodo.

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
