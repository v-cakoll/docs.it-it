---
title: Confronto di DataRows (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 2b45a4629474c394c8e49c41a7a98fc1181e124b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077173"
---
# <a name="comparing-datarows-linq-to-dataset"></a>Confronto di DataRows (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] definisce diversi operatori sui set per confrontare gli elementi di origine per verificare se sono uguali. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] fornisce gli operatori sui set seguenti:  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 Questi operatori confrontano gli elementi di origine chiamando i metodi <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> e <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> su ogni raccolta di elementi. Nel caso di un oggetto <xref:System.Data.DataRow>, questi operatori eseguono un confronto di riferimento, che tuttavia non corrisponde in genere al comportamento ideale per le operazioni sui set eseguite su dati tabulari. Per le operazioni sui set si desidera in genere stabilire se i valori degli elementi, e non i riferimenti agli elementi, sono uguali. Per questo motivo a <xref:System.Data.DataRowComparer> è stata aggiunta la classe [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Questa classe può essere utilizzata per confrontare i valori di riga.  
  
 La classe <xref:System.Data.DataRowComparer> contiene un'implementazione del confronto di valori per <xref:System.Data.DataRow>, pertanto può essere usata per operazioni sui set, ad esempio <xref:System.Linq.Enumerable.Distinct%2A>. Non è possibile creare direttamente un'istanza di questa classe ed è invece necessario usare la proprietà <xref:System.Data.DataRowComparer.Default%2A> per restituire un'istanza di <xref:System.Data.DataRowComparer%601>. Viene quindi chiamato il metodo <xref:System.Data.DataRowComparer%601.Equals%2A> e i due oggetti <xref:System.Data.DataRow> da confrontare vengono passati come parametri di input. Il metodo <xref:System.Data.DataRowComparer%601.Equals%2A> restituisce `true` se il set ordinato di valori di colonna è uguale in entrambi gli oggetti <xref:System.Data.DataRow>; in caso contrario, `false`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato `Intersect` per restituire i contatti presenti in entrambe le tabelle.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente vengono confrontate due righe e ne vengono ottenuti i codici hash.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRowComparer>
- [Caricamento di dati in un dataset](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
