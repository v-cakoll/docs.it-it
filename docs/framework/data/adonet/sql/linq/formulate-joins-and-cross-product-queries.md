---
title: Formulare query su prodotto incrociato e join
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b21bee335c5856c961c5abc21ad03c5d1f2c2307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a>Formulare query su prodotto incrociato e join
Negli esempi riportati di seguito viene illustrato come combinare risultati da più tabelle.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la navigazione con chiave esterna nel `From` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clausola in c#) per selezionare tutti gli ordini per i clienti di Londra.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la navigazione con chiave esterna nel `Where` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clausola in c#) per filtrare per out-of-stock `Products` cui `Supplier` è negli Stati Uniti.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la navigazione con chiave esterna nella clausola `From` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (la clausola `from` in C#) per filtrare i dipendenti di Seattle ed elencare i territori.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la navigazione con chiave esterna nel `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) per filtrare le coppie di dipendenti in cui un dipendente riporta a altro ed entrambi sono della stessa `City`.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>Esempio  
 Le operazioni seguenti [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] esempio cerca tutti i clienti e ordini, viene controllato che gli ordini siano associati ai clienti e garantisce che per ogni cliente nell'elenco, viene fornito un nome di contatto.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono unite in join in modo esplicito due tabelle e vengono proiettati i risultati da entrambe le tabelle.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono unite in join in modo esplicito tre tabelle e vengono proiettati i risultati da ogni tabella.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come ottenere `LEFT OUTER JOIN` usando `DefaultIfEmpty()`. Il metodo `DefaultIfEmpty()` restituisce null se non è presente alcun `Order` per `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene proiettata l'espressione `let` risultante da un join.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un `join` con una chiave composita.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene descritto come costruire un `join` in cui un solo lato è nullable.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
