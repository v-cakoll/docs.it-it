---
title: 'Esempi di sintassi delle espressioni di query: Operatori di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: e80c50daeb0de7f4a8477786f28441d1495033ea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249480"
---
# <a name="query-expression-syntax-examples-join-operators"></a>Esempi di sintassi delle espressioni di query: Operatori di join
La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali. Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati. Per ulteriori informazioni, vedere [Cenni preliminari sugli operatori di query standard](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).  
  
 Negli esempi di questo argomento viene illustrato come utilizzare i <xref:System.Linq.Enumerable.GroupJoin%2A> metodi <xref:System.Linq.Enumerable.Join%2A> e per eseguire query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando la sintassi delle espressioni di query. Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente. Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto. Vengono visualizzati l'ID e il numero di ordini per ogni contatto.  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>Unisci  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito un join sulle tabelle SalesOrderHeader e SalesOrderDetail per ottenere gli ordini effettuati online dal mese di agosto.  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>Vedere anche

- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
