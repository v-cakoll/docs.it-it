---
title: Eseguire una sottoquery su un'operazione di raggruppamento (LINQ in C#)
description: Come eseguire una sottoquery su un'operazione di raggruppamento usando LINQ in C#.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 76e54cc6b29090a8464400ae6460812dd9ad86f9
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404116"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Eseguire una sottoquery su un'operazione di raggruppamento

Questo articolo descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo. La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`. La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna. Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.  
  
Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).  
  
Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md). L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.  
  
## <a name="example"></a>Esempio

> [!NOTE]
> Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  

## <a name="see-also"></a>Vedere anche

[LINQ (Language-Integrated Query)](index.md)
