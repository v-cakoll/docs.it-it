---
title: 'Esempi di sintassi delle espressioni di query: Spostamento tra relazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
ms.openlocfilehash: a99d7d31ce23629bf7a0f390244c1fe67b4554e3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854403"
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a>Esempi di sintassi delle espressioni di query: Spostamento tra relazioni
Le proprietà di navigazione nel Entity Framework sono proprietà di collegamento utilizzate per individuare le entità finali di un'associazione. Le proprietà di navigazione consentono a un utente di spostarsi da un'entità a un'altra o da un entità alle entità correlate tramite un set di associazioni. In questo argomento vengono forniti esempi nella sintassi delle espressioni di query per spostarsi tra le relazioni tramite le proprietà di navigazione nelle query LINQ to Entities.  
  
 Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per ottenere tutti gli ID contatto e la somma del totale dovuto per ogni contatto il cui cognome è "Zhou". La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto. Il metodo `Sum` usa la proprietà di navigazione `Contact.SalesOrderHeader` per sommare il totale dovuto per tutti gli ordini per ciascun contatto.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono ottenuti tutti gli ordini dei contatti il cui cognome è "Zhou". La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto. Il nome e gli ordini del contatto vengono restituiti in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono usate le proprietà di navigazione `SalesOrderHeader.Address` e `SalesOrderHeader.Contact` per ottenere la raccolta di oggetti `Address` e `Contact` associati a ogni ordine. Il cognome del contatto, l'indirizzo, il numero dell'ordine di vendita e il totale dovuto per ogni ordine alla città di Seattle vengono restituiti in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo `Where` per individuare gli ordini effettuati dopo l'1 dicembre 2003, quindi viene usata la proprietà di navigazione `order.SalesOrderDetail` per ottenere i dettagli relativi a ogni ordine.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a>Vedere anche

- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
