---
title: 'Procedura: eseguire una query per ottenere informazioni'
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
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 527c2c1a84126bc2012779345fdd98ad832c9ceb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-query-for-information"></a>Procedura: eseguire una query per ottenere informazioni
Le query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usano la stessa sintassi delle query in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. L'unica differenza è che gli oggetti a cui fa riferimento [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query viene eseguito il mapping agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione.  
  
 Alcune funzionalità delle query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] potrebbero richiedere un'attenzione speciale nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per ulteriori informazioni, vedere [concetti relativi alle Query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## <a name="example"></a>Esempio  
 La query seguente consente di richiedere un elenco di clienti nell'area londinese. In questo esempio `Customers` è una tabella nel database di esempio Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
