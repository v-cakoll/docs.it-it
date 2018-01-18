---
title: Query su tabella incrociata (LINQ to DataSet)
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
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ede3cef32fc752239dfbed6a05adbdb1cc5bfbe
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="cross-table-queries-linq-to-dataset"></a>Query su tabella incrociata (LINQ to DataSet)
Oltre alle query su singola tabella, è possibile eseguire query tra tabelle in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Questa operazione viene eseguita utilizzando un *join*. Per join si intende l'associazione degli oggetti di un'origine dati con oggetti di un'altra origine dati che condividono un attributo comune, ad esempio un ID prodotto o contatto. Nella programmazione orientata a oggetti, lo spostamento nelle relazioni tra oggetti è relativamente semplice, perché ogni oggetto include un membro che fa riferimento a un altro oggetto. Nelle tabelle di database esterne, tuttavia, lo spostamento nelle relazioni non è un processo così semplice. Le tabelle di database non contengono relazioni predefinite. In questi casi, l'operazione join può essere utilizzata per far corrispondere gli elementi di ogni origine. Ad esempio, date due tabelle contenenti informazioni sui prodotti e sulle vendite, è possibile usare un'operazione join per creare una corrispondenza tra le informazioni sulle vendite e i prodotti relativi allo stesso ordine di vendita.  
  
 Nel framework [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] sono disponibili due operatori join, <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A>. Questi operatori eseguono *equijoin*:, ovvero join che corrispondono a dati di due origini solo quando le chiavi sono uguali. Al contrario, in [!INCLUDE[tsql](../../../../includes/tsql-md.md)] sono supportati operatori di join diversi da `equals`, ad esempio l'operatore `less than`.  
  
 In termini di database relazionale, il metodo <xref:System.Linq.Enumerable.Join%2A> implementa un inner join. Un inner join è un tipo di join in cui vengono restituiti solo gli oggetti che dispongono di una corrispondenza nel set di dati opposto.  
  
 Il <xref:System.Linq.Enumerable.GroupJoin%2A> operatori hanno un equivalente diretto in termini di database relazionale, ma implementano un superset di inner join e left outer join. Un left outer join è un join che restituisce ogni elemento della prima raccolta (sinistra), anche se non ha elementi correlati nella seconda raccolta.  
  
 Per ulteriori informazioni sui join, vedere [operazioni Join](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito un join tradizionale delle tabelle `SalesOrderHeader` e `SalesOrderDetail` del database di esempio AdventureWorks per ottenere gli ordini effettuati online dal mese di agosto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di query su oggetti DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Query su singola tabella](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [Esecuzione di query su oggetti DataSet tipizzati](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [Operazioni di join](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
