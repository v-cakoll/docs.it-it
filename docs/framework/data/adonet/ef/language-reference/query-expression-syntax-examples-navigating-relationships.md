---
title: 'Esempi di sintassi di espressione di query: esplorazione di relazioni'
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
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d86fa3aab55daff9c7a3724c93ad68be27a6908b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="b73b2-102">Esempi di sintassi di espressione di query: esplorazione di relazioni</span><span class="sxs-lookup"><span data-stu-id="b73b2-102">Query Expression Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="b73b2-103">Le proprietà di navigazione in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono proprietà di collegamento usate per individuare le entità finali di un'associazione.</span><span class="sxs-lookup"><span data-stu-id="b73b2-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="b73b2-104">Le proprietà di navigazione consentono a un utente di spostarsi da un'entità a un'altra o da un entità alle entità correlate tramite un set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="b73b2-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="b73b2-105">In questo argomento sono inclusi alcuni esempi nella sintassi delle espressioni di query in cui viene illustrato come spostarsi tra relazioni tramite proprietà di navigazione in query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b73b2-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="b73b2-106">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b73b2-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b73b2-107">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="b73b2-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="b73b2-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b73b2-108">Example</span></span>  
 <span data-ttu-id="b73b2-109">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per ottenere tutti gli ID contatto e la somma del totale dovuto per ogni contatto il cui cognome è "Zhou".</span><span class="sxs-lookup"><span data-stu-id="b73b2-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="b73b2-110">La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="b73b2-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="b73b2-111">Il metodo `Sum` usa la proprietà di navigazione `Contact.SalesOrderHeader` per sommare il totale dovuto per tutti gli ordini per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="b73b2-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="b73b2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b73b2-112">Example</span></span>  
 <span data-ttu-id="b73b2-113">Nell'esempio seguente vengono ottenuti tutti gli ordini dei contatti il cui cognome è "Zhou".</span><span class="sxs-lookup"><span data-stu-id="b73b2-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="b73b2-114">La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="b73b2-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="b73b2-115">Il nome e gli ordini del contatto vengono restituiti in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="b73b2-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="b73b2-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b73b2-116">Example</span></span>  
 <span data-ttu-id="b73b2-117">Nell'esempio seguente vengono usate le proprietà di navigazione `SalesOrderHeader.Address` e `SalesOrderHeader.Contact` per ottenere la raccolta di oggetti `Address` e `Contact` associati a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="b73b2-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="b73b2-118">Il cognome del contatto, l'indirizzo, il numero dell'ordine di vendita e il totale dovuto per ogni ordine alla città di Seattle vengono restituiti in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="b73b2-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="b73b2-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b73b2-119">Example</span></span>  
 <span data-ttu-id="b73b2-120">Nell'esempio seguente viene usato il metodo `Where` per individuare gli ordini effettuati dopo l'1 dicembre 2003, quindi viene usata la proprietà di navigazione `order.SalesOrderDetail` per ottenere i dettagli relativi a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="b73b2-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="b73b2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b73b2-121">See Also</span></span>  
 [<span data-ttu-id="b73b2-122">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b73b2-122">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
