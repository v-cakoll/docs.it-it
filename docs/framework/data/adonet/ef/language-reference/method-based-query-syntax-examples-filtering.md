---
title: 'Esempi di sintassi delle query basate su metodo: Filtro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: 1064e4f8d4fce16d0505eb79b5e862be7c2e4ce6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111371"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="d191d-102">Esempi di sintassi delle query basate su metodo: Filtro</span><span class="sxs-lookup"><span data-stu-id="d191d-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="d191d-103">Gli esempi in questo argomento illustrano come usare il `Where` e `Where…Contains` metodi per eseguire una query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="d191d-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="d191d-104">Si noti che, in cui...`Contains`</span><span class="sxs-lookup"><span data-stu-id="d191d-104">Note, Where…`Contains`</span></span> <span data-ttu-id="d191d-105">non può essere usato come parte di un [query compilata](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="d191d-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="d191d-106">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d191d-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d191d-107">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="d191d-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="d191d-108">Dove</span><span class="sxs-lookup"><span data-stu-id="d191d-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="d191d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-109">Example</span></span>  
 <span data-ttu-id="d191d-110">Nell'esempio seguente vengono restituiti tutti gli ordini online.</span><span class="sxs-lookup"><span data-stu-id="d191d-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="d191d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-111">Example</span></span>  
 <span data-ttu-id="d191d-112">Nell'esempio seguente vengono restituiti gli ordini in cui la quantità ordinata è maggiore di 2 e minore di 6.</span><span class="sxs-lookup"><span data-stu-id="d191d-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="d191d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-113">Example</span></span>  
 <span data-ttu-id="d191d-114">Nell'esempio seguente vengono restituiti tutti i prodotti di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="d191d-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="d191d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-115">Example</span></span>  
 <span data-ttu-id="d191d-116">Nell'esempio seguente viene usato il metodo `Where` per individuare gli ordini effettuati dopo l'1 dicembre 2003, quindi viene usata la proprietà di navigazione `order.SalesOrderDetail` per ottenere i dettagli relativi a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="d191d-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="d191d-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="d191d-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="d191d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-118">Example</span></span>  
 <span data-ttu-id="d191d-119">Nell'esempio seguente viene usata una matrice come parte di una clausola `Where…Contains` per trovare tutti i prodotti con un `ProductModelID` che corrisponde a un valore nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d191d-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="d191d-120">Come parte del predicato in una clausola `Where…Contains`, è possibile usare un oggetto <xref:System.Array>, un oggetto <xref:System.Collections.Generic.List%601>o una raccolta di qualsiasi tipo che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d191d-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="d191d-121">È inoltre possibile dichiarare e inizializzare una raccolta all'interno di una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d191d-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="d191d-122">Per altre informazioni, vedere l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="d191d-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d191d-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="d191d-123">Example</span></span>  
 <span data-ttu-id="d191d-124">Nell'esempio seguente vengono dichiarate e inizializzate matrici in una clausola `Where…Contains` per trovare tutti i prodotti che dispongono di un `ProductModelID` o una `Size` che corrisponde a un valore nelle matrici.</span><span class="sxs-lookup"><span data-stu-id="d191d-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d191d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d191d-125">See also</span></span>

- [<span data-ttu-id="d191d-126">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d191d-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
