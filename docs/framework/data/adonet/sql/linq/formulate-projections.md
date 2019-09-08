---
title: Formulare proiezioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793821"
---
# <a name="formulate-projections"></a>Formulare proiezioni
Negli esempi seguenti viene illustrato il `select` modo in C# cui `Select` l'istruzione nell'istruzione e in Visual Basic può essere combinata con altre funzionalità per formare le proiezioni della query.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata `Select` la clausola in Visual Basic`select` (clausola C#in) per restituire una sequenza di nomi di `Customers`contatto per.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select` la clausola in Visual Basic`select` (clausola C#in) e i *tipi anonimi* per restituire una sequenza di nomi di contatto `Customers`e numeri di telefono per.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select` la clausola in Visual Basic`select` (clausola C#in) e i *tipi anonimi* per restituire una sequenza di nomi e numeri di telefono per i dipendenti. I `FirstName` campi `LastName` e vengono combinati in un singolo campo`Name`() `Phone` e il `HomePhone` campo viene rinominato nella sequenza risultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata `Select` la clausola in Visual Basic`select` (clausola C#in) e i *tipi anonimi* per restituire una `ProductID`sequenza di tutti i e un `HalfPrice`valore calcolato denominato. Questo valore viene impostato su `UnitPrice` e diviso per 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select` la clausola in Visual Basic`select` (clausola C#in) e un' *istruzione condizionale* per restituire una sequenza di nome prodotto e disponibilità del prodotto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata una `Select` clausola Visual Basic`select` (clausola C#in) e un *tipo conosciuto* (Name) per restituire una sequenza dei nomi dei dipendenti.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono `Select` usati `Where` e in Visual Basic`select` ( `where` e C#in) per restituire una *sequenza filtrata* di nomi di contatto per i clienti di Londra.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select` una clausola in Visual Basic`select` (clausola C#in) e i *tipi anonimi* per restituire un *subset con forma* di dati relativi ai clienti.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono usate query annidate per restituire i risultati riportati di seguito:  
  
- Una sequenza di tutti gli ordini e dei corrispondenti `OrderID`.  
  
- Una sottosequenza degli elementi nell'ordine per cui è presente uno sconto.  
  
- L'importo risparmiato se il costo di spedizione non è incluso.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
