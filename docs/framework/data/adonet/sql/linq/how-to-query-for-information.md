---
title: 'Procedura: Eseguire una query per ottenere informazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ed32bbe7d27357cbed7d77dd235b698a65c0e29e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793532"
---
# <a name="how-to-query-for-information"></a>Procedura: Eseguire una query per ottenere informazioni
Le query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usano la stessa sintassi delle query in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. L'unica differenza è che gli oggetti a cui viene [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fatto riferimento nelle query vengono mappati agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione.  
  
 Alcune funzionalità delle query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] potrebbero richiedere un'attenzione speciale nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per altre informazioni, vedere [concetti relativi alle query](query-concepts.md).  
  
## <a name="example"></a>Esempio  
 La query seguente consente di richiedere un elenco di clienti nell'area londinese. In questo esempio `Customers` è una tabella nel database di esempio Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Creazione del modello a oggetti](creating-the-object-model.md)
- [Download di database di esempio](downloading-sample-databases.md)
- [Esecuzione di query sul database](querying-the-database.md)
