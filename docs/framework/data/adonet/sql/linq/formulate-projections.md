---
title: Formulare proiezioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f554007bd8c9e69f6a8dc475c122d3fbdfc43a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="formulate-projections"></a>Formulare proiezioni
Gli esempi seguenti illustrano il modo in cui `select` istruzione nel linguaggio c# e `Select` istruzione in Visual Basic può essere combinata con altre funzionalità per formare proiezioni della query.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) per restituire una sequenza di nomi di contatti per `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi di contatti e numeri di telefono per `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi e i numeri di telefono per i dipendenti. Il `FirstName` e `LastName` campi vengono combinati in un singolo campo (`Name`) e `HomePhone` campo viene rinominato in `Phone` nella sequenza risultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di tutti i `ProductID`s e un valore calcolato denominato `HalfPrice`. Questo valore viene impostato su `UnitPrice` e diviso per 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e una *istruzione condizionale* per restituire una sequenza di disponibilità del prodotto e nome del prodotto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un Visual Basic `Select` clausola (`select` clausola in c#) e una *tipo conosciuto* (Name) per restituire una sequenza di nomi di dipendenti.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select` e `Where` in Visual Basic (`select` e `where` in c#) per restituire un *sequenza filtrata* di nomi di contatti per i clienti di Londra.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire un *subset con shaping* dei dati sui clienti.  
  
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
