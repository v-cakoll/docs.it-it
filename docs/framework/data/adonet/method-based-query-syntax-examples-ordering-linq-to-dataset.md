---
title: 'Esempi di sintassi delle query basate su metodo: Ordinamento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 16a37cb0bc36741ad816d2aa038a1390e3282d9b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794986"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a>Esempi di sintassi delle query basate su metodo: Ordinamento (LINQ to DataSet)
Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A> e <xref:System.Linq.Enumerable.ThenBy%2A> per eseguire una query su <xref:System.Data.DataSet> e ordinare i risultati usando la sintassi delle query basate su metodo.  
  
 Il `FillDataSet` metodo utilizzato in questi esempi viene specificato nel [caricamento di dati in un DataSet](loading-data-into-a-dataset.md).  
  
 Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="orderby"></a>OrderBy  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.OrderBy%2A> con un operatore di confronto personalizzato per ordinare i cognomi senza distinzione tra maiuscole e minuscole.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a>Reverse  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Reverse%2A> per creare un elenco di ordini in cui il valore di `OrderDate` è precedente al 20 febbraio 2002.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>Esempio  
 In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.ThenBy%2A> con un operatore di confronto personalizzato per ordinare prima in base al prezzo di listino e quindi applicare l'ordinamento discendente e senza distinzione tra maiuscole e minuscole ai nomi di prodotto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a>Vedere anche

- [Caricamento di dati in un oggetto DataSet](loading-data-into-a-dataset.md)
- [Esempi di LINQ to DataSet](linq-to-dataset-examples.md)
- [Panoramica degli operatori di query standard (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Panoramica degli operatori query standard (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
