---
title: Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione
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
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b9b79915e94ed1015c7869692647c10da58f60
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione
L'operatore <xref:System.Linq.Enumerable.All%2A> restituisce `true` se tutti gli elementi in una sequenza soddisfanno una condizione.  
  
 L'operatore <xref:System.Linq.Queryable.Any%2A> restituisce `true` se un elemento qualsiasi in una sequenza soddisfa una condizione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene restituita una sequenza di clienti con almeno un ordine. Il `Where` / `where` clausola restituisce `true` se il dato `Customer` presenti `Order`.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Esempio  
 Il codice Visual Basic seguente determina l'elenco di clienti che non hanno effettuato ordini e assicura che per ogni cliente nell'elenco venga fornito un nome di contatto.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio C# seguente viene restituita una sequenza di clienti i cui ordini contengono un elemento `ShipCity` che inizia con la lettera specificata. Nei risultati vengono restituiti anche i clienti che non hanno effettuato ordini. In base alla progettazione, l'operatore <xref:System.Linq.Queryable.All%2A> restituisce `true` per una sequenza vuota. I clienti senza ordini vengono eliminati nell'output della console usando l'operatore `Count`.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
