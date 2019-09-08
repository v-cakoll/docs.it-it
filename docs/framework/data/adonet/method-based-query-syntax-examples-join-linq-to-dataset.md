---
title: 'Esempi di sintassi delle query basate su metodo: Join (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: ba6e33f98e063aab946db27b97106272c5adef63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783664"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a>Esempi di sintassi delle query basate su metodo: Join (LINQ to DataSet)
La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali. Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati. Per ulteriori informazioni, vedere Cenni preliminari [sugli operatoriC#di query standard ()](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [Cenni preliminari sugli operatori di query standard (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 Negli esempi di questo argomento viene illustrato l'uso del metodo <xref:System.Linq.Enumerable.Join%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle query basate su metodo.  
  
 Il `FillDataSet` metodo utilizzato in questi esempi viene specificato nel [caricamento di dati in un DataSet](loading-data-into-a-dataset.md).  
  
 Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="join"></a>Unisci  
  
### <a name="example"></a>Esempio  
 In questo esempio viene eseguito un join sulle tabelle `Contact` e `SalesOrderHeader`.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a>Esempio  
 In questo esempio viene eseguito un join sulle tabelle `Contact` e `SalesOrderHeader`, raggruppando i risultati in base a ID contatto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a>Vedere anche

- [Caricamento di dati in un oggetto DataSet](loading-data-into-a-dataset.md)
- [Esempi di LINQ to DataSet](linq-to-dataset-examples.md)
- [Panoramica degli operatori di query standard (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Panoramica degli operatori query standard (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Esempi di join](https://go.microsoft.com/fwlink/?LinkId=187357)
- [Esempi di DataSet](https://go.microsoft.com/fwlink/?LinkId=187358)
