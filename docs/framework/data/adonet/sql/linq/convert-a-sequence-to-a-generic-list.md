---
title: Convertire una sequenza un tipo in un elenco generico
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
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e563e0ed46bfdadca9923b582f2c30e12701d992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertire una sequenza un tipo in un elenco generico
Usare <xref:System.Linq.Enumerable.ToList%2A> per creare un elenco generico da una sequenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.ToList%2A> per valutare immediatamente una query in un oggetto <xref:System.Collections.Generic.List%601> generico.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
