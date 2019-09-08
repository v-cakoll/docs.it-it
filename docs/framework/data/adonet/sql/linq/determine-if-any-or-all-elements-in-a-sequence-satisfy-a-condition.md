---
title: Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: 7de65579cb41641aded0b9a320fac59804959ff5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782224"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione
L'operatore <xref:System.Linq.Enumerable.All%2A> restituisce `true` se tutti gli elementi in una sequenza soddisfanno una condizione.  
  
 L'operatore <xref:System.Linq.Queryable.Any%2A> restituisce `true` se un elemento qualsiasi in una sequenza soddisfa una condizione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene restituita una sequenza di clienti con almeno un ordine. La `Where` / clausolarestituisce`true` se l'oggetto specificato`Customer` contiene .`Order` `where`  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Esempio  
 Il codice Visual Basic seguente determina l'elenco di clienti che non hanno effettuato ordini e assicura che per ogni cliente nell'elenco venga fornito un nome di contatto.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio C# seguente viene restituita una sequenza di clienti i cui ordini contengono un elemento `ShipCity` che inizia con la lettera specificata. Nei risultati vengono restituiti anche i clienti che non hanno effettuato ordini. In base alla progettazione, l'operatore <xref:System.Linq.Queryable.All%2A> restituisce `true` per una sequenza vuota. I clienti senza ordini vengono eliminati nell'output della console usando l'operatore `Count`.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
