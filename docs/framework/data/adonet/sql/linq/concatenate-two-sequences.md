---
title: Concatenare due sequenze
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a>Concatenare due sequenze
Usare l'operatore <xref:System.Linq.Queryable.Concat%2A> per concatenare due sequenze.  
  
 L'operatore <xref:System.Linq.Queryable.Concat%2A> viene definito per multiset ordinati in cui gli ordini del ricevente e dell'argomento sono gli stessi.  
  
 L'ordinamento in SQL è il passaggio finale prima della generazione dei risultati. Per questo motivo l'operatore <xref:System.Linq.Queryable.Concat%2A> viene implementato usando `UNION ALL` e non mantiene l'ordine dei relativi argomenti. Per essere certi che l'ordine nei risultati sia corretto, ordinarli in modo esplicito.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato <xref:System.Linq.Queryable.Concat%2A> per restituire una sequenza di tutti i numeri di telefono e di fax relativi a `Customer` e `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato <xref:System.Linq.Queryable.Concat%2A> per restituire una sequenza di tutti i mapping di nomi e numeri di telefono relativi a `Customer` e `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Conversione dell'operatore di Query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
