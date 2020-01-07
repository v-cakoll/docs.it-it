---
title: 'Procedura: eseguire una query per ottenere informazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634651"
---
# <a name="how-to-query-for-information"></a>Procedura: eseguire una query per ottenere informazioni
Le query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizzano la stessa sintassi delle query in LINQ. L'unica differenza è che agli oggetti a cui viene fatto riferimento nelle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione.  
  
 Alcune funzionalità delle query LINQ potrebbero richiedere particolare attenzione nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per altre informazioni, vedere [concetti relativi alle query](query-concepts.md).  
  
## <a name="example"></a>Esempio  
 La query seguente consente di richiedere un elenco di clienti nell'area londinese. In questo esempio `Customers` è una tabella nel database di esempio Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Creazione del modello a oggetti](creating-the-object-model.md)
- [Download di database di esempio](downloading-sample-databases.md)
- [Esecuzione di query sul database](querying-the-database.md)
