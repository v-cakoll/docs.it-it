---
title: 'Esempi di sintassi di query basate sul metodo: operatori di elemento (LINQ to DataSet)'
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
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ba6a774c0e270cda1e139ab9ddb9233e994c3f12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a>Esempi di sintassi di query basate sul metodo: operatori di elemento (LINQ to DataSet)
Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.First%2A> e <xref:System.Linq.Enumerable.ElementAt%2A> per ottenere elementi di <xref:System.Data.DataRow> da <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.  
  
 Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="elementat"></a>ElementAt  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.ElementAt%2A> per recuperare il quinto indirizzo in cui `PostalCode` == "M4B 1V7".  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a>First  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.First%2A> per restituire il primo contatto il cui nome è 'Brooke'.  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a>Vedere anche  
 [Caricamento di dati in un oggetto DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Cenni preliminari sugli operatori di query standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
