---
title: Eseguire una sottoquery su un'operazione di raggruppamento
description: Come eseguire una sottoquery su un'operazione di raggruppamento.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: f638b8a679a15891d04e02f1597d6bf7934a9e74
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Eseguire una sottoquery su un'operazione di raggruppamento

Questo argomento descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo. La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`. La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna. Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.  
  
 Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).  
  
 Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md). L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.  
  
## <a name="example"></a>Esempio 

 > [!NOTE]
 > Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a>Vedere anche  
 [Espressioni di query LINQ](index.md)
