---
title: Formulare proiezioni
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bb22ddd4882d9885c55301a6fdc6a0eb336b49af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-projections"></a>Formulare proiezioni
Negli esempi seguenti viene illustrato come è possibile combinare l'istruzione `select` in C# e l'istruzione `Select` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] con altre funzionalità per formare proiezioni della query.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) per restituire una sequenza di nomi di contatti per `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi di contatti e numeri di telefono per `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi e numeri di telefono per i dipendenti. Il `FirstName` e `LastName` campi vengono combinati in un singolo campo (`Name`) e `HomePhone` campo viene rinominato in `Phone` nella sequenza risultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di tutti i `ProductID`s e un valore calcolato denominato `HalfPrice`. Questo valore viene impostato su `UnitPrice` e diviso per 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e un *istruzione condizionale* per restituire una sequenza di disponibilità del prodotto e nome del prodotto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clausola (`select` clausola in c#) e un *tipo conosciuto* (Name) per restituire una sequenza di nomi dei dipendenti.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa `Select` e `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` e `where` in c#) per restituire un *sequenza filtrata* nomi di contatti per i clienti di Londra.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire un *subset con shaping* dei dati sui clienti.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono usate query annidate per restituire i risultati riportati di seguito:  
  
-   Una sequenza di tutti gli ordini e dei corrispondenti `OrderID`.  
  
-   Una sottosequenza degli elementi nell'ordine per cui è presente uno sconto.  
  
-   L'importo risparmiato se il costo di spedizione non è incluso.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
