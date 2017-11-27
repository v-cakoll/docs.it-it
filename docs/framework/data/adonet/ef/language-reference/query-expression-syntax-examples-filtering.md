---
title: 'Esempi di sintassi dell''espressione di query: filtro'
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
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e943dc85f46d3cf9f1f3a9032b70b17cf4a72a66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-filtering"></a><span data-ttu-id="b9f9a-102">Esempi di sintassi dell'espressione di query: filtro</span><span class="sxs-lookup"><span data-stu-id="b9f9a-102">Query Expression Syntax Examples: Filtering</span></span>
<span data-ttu-id="b9f9a-103">Negli esempi in questo argomento viene illustrato come utilizzare il `Where` e `Where…Contains` metodi per eseguire una query di [modello Sales di AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="b9f9a-104">Si noti che in...`Contains`</span><span class="sxs-lookup"><span data-stu-id="b9f9a-104">Note, Where…`Contains`</span></span> <span data-ttu-id="b9f9a-105">non può essere utilizzato come parte di un [query compilata](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="b9f9a-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="b9f9a-106">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b9f9a-107">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="b9f9a-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="b9f9a-108">Dove</span><span class="sxs-lookup"><span data-stu-id="b9f9a-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="b9f9a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-109">Example</span></span>  
 <span data-ttu-id="b9f9a-110">Nell'esempio seguente vengono restituiti tutti gli ordini online.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a><span data-ttu-id="b9f9a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-111">Example</span></span>  
 <span data-ttu-id="b9f9a-112">Nell'esempio seguente vengono restituiti gli ordini in cui la quantità ordinata è maggiore di 2 e minore di 6.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a><span data-ttu-id="b9f9a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-113">Example</span></span>  
 <span data-ttu-id="b9f9a-114">Nell'esempio seguente vengono restituiti tutti i prodotti di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a><span data-ttu-id="b9f9a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-115">Example</span></span>  
 <span data-ttu-id="b9f9a-116">Nell'esempio seguente viene usato il metodo `Where` per individuare gli ordini effettuati dopo l'1 dicembre 2003, quindi viene usata la proprietà di navigazione `order.SalesOrderDetail` per ottenere i dettagli relativi a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-116">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a><span data-ttu-id="b9f9a-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="b9f9a-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="b9f9a-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-118">Example</span></span>  
 <span data-ttu-id="b9f9a-119">Nell'esempio seguente viene usata una matrice come parte di una clausola `Where…Contains` per trovare tutti i prodotti con un `ProductModelID` che corrisponde a un valore nella matrice.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="b9f9a-120">Come parte del predicato in una clausola `Where…Contains`, è possibile usare un oggetto <xref:System.Array>, un oggetto <xref:System.Collections.Generic.List%601>o una raccolta di qualsiasi tipo che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b9f9a-121">È inoltre possibile dichiarare e inizializzare una raccolta all'interno di una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="b9f9a-122">Per altre informazioni, vedere l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="b9f9a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f9a-123">Example</span></span>  
 <span data-ttu-id="b9f9a-124">Nell'esempio seguente vengono dichiarate e inizializzate delle matrici in una clausola `Where…Contains` per trovare tutti i prodotti nei quali `ProductModelID` o `Size` corrisponde ai valori nelle matrici.</span><span class="sxs-lookup"><span data-stu-id="b9f9a-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or `Size` that match values in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b9f9a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9f9a-125">See Also</span></span>  
 [<span data-ttu-id="b9f9a-126">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b9f9a-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
