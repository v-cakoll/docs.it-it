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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 066ea4d3c4232137fa6dbd758c8a3be1feec9e61
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertire una sequenza un tipo in un elenco generico
Usare <xref:System.Linq.Enumerable.ToList%2A> per creare un elenco generico da una sequenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.ToList%2A> per valutare immediatamente una query in un oggetto <xref:System.Collections.Generic.List%601> generico.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
