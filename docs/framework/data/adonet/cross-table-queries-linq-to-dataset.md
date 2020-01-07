---
title: Query su tabella incrociata (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 8f9a538482580134fa876866dfe394c3dfc7de2a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634885"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Query su tabella incrociata (LINQ to DataSet)
Oltre a eseguire query su una singola tabella, è anche possibile eseguire query tra tabelle in LINQ to DataSet. Questa operazione viene eseguita usando un *join*. Per join si intende l'associazione degli oggetti di un'origine dati con oggetti di un'altra origine dati che condividono un attributo comune, ad esempio un ID prodotto o contatto. Nella programmazione orientata a oggetti, lo spostamento nelle relazioni tra oggetti è relativamente semplice, perché ogni oggetto include un membro che fa riferimento a un altro oggetto. Nelle tabelle di database esterne, tuttavia, lo spostamento nelle relazioni non è un processo così semplice. Le tabelle di database non contengono relazioni predefinite. In questi casi, l'operazione join può essere utilizzata per far corrispondere gli elementi di ogni origine. Ad esempio, date due tabelle contenenti informazioni sui prodotti e sulle vendite, è possibile usare un'operazione join per creare una corrispondenza tra le informazioni sulle vendite e i prodotti relativi allo stesso ordine di vendita.  
  
 Il framework LINQ (Language-Integrated Query) fornisce due operatori di join, <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A>. Questi operatori eseguono *equi-join*, ovvero join che corrispondono a due origini dati solo quando le relative chiavi sono uguali. Al contrario, Transact-SQL supporta operatori join diversi da `equals`, ad esempio l'operatore `less than`.  
  
 In termini di database relazionale, il metodo <xref:System.Linq.Enumerable.Join%2A> implementa un inner join. Un inner join è un tipo di join in cui vengono restituiti solo gli oggetti che dispongono di una corrispondenza nel set di dati opposto.  
  
 Gli operatori <xref:System.Linq.Enumerable.GroupJoin%2A> non hanno equivalenti diretti in termini di database relazionale. implementano un superset di Inner join e left outer join. Un left outer join è un join che restituisce ogni elemento della prima raccolta (sinistra), anche se non ha elementi correlati nella seconda raccolta.  
  
 Per ulteriori informazioni sui join, vedere [operazioni di join](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito un join tradizionale delle tabelle `SalesOrderHeader` e `SalesOrderDetail` del database di esempio AdventureWorks per ottenere gli ordini effettuati online dal mese di agosto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di query su oggetti DataSet](querying-datasets-linq-to-dataset.md)
- [Query su singola tabella](single-table-queries-linq-to-dataset.md)
- [Esecuzione di query su oggetti DataSet tipizzati](querying-typed-datasets.md)
- [Operazioni di join](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))
- [Esempi di LINQ to DataSet](linq-to-dataset-examples.md)
