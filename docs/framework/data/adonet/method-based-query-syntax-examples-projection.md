---
title: 'Esempi di sintassi di query basate sul metodo: proiezione (LINQ to DataSet)'
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
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 879754e0604b9dfa6a6ffc7b7777094cc156befb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a>Esempi di sintassi di query basate sul metodo: proiezione (LINQ to DataSet)
Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.Select%2A> e <xref:System.Linq.Enumerable.SelectMany%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle query basate su metodo.  
  
 Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="select"></a>Seleziona  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Select%2A> per proiettare le proprietà `Name` e `ProductNumber` `ListPrice` in una sequenza di tipi anonimi.  La proprietà `ListPrice` viene inoltre rinominata in  `Price` nel tipo risultante.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a>SelectMany  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini in cui `TotalDue` è minore di 500,00.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini che sono stati effettuati a partire dall'1 ottobre 2002.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a>Vedere anche  
 [Caricamento di dati in un oggetto DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Cenni preliminari sugli operatori di query standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
