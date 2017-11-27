---
title: Ordinare elementi in una sequenza
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
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2f4f89c1391b6582d77acccb8b256bef617ecff3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="60822-102">Ordinare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="60822-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="60822-103">Usare l'operatore <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare una sequenza in base a una o più chiavi.</span><span class="sxs-lookup"><span data-stu-id="60822-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="60822-104">è progettato per supportare l'ordinamento in base a semplici tipi primitivi, ad esempio `string`, `int`e così via.</span><span class="sxs-lookup"><span data-stu-id="60822-104"> is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="60822-105">Non supporta invece l'ordinamento per classi multivalore complesse, ad esempio i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="60822-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="60822-106">Non supporta inoltre i tipi di dati `byte`.</span><span class="sxs-lookup"><span data-stu-id="60822-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60822-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-107">Example</span></span>  
 <span data-ttu-id="60822-108">Nell'esempio seguente vengono ordinati `Employees` in base alla data di assunzione.</span><span class="sxs-lookup"><span data-stu-id="60822-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="60822-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-109">Example</span></span>  
 <span data-ttu-id="60822-110">Nell'esempio seguente viene usato `where` per l'ordinamento di `Orders` spediti a `London` in base al costo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="60822-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="60822-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-111">Example</span></span>  
 <span data-ttu-id="60822-112">Nell'esempio seguente vengono ordinati `Products` in base al prezzo unitario dal più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="60822-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="60822-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-113">Example</span></span>  
 <span data-ttu-id="60822-114">Nell'esempio seguente viene usato il tipo `OrderBy` composto per ordinare `Customers` in base alla città, quindi al nome del contatto.</span><span class="sxs-lookup"><span data-stu-id="60822-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="60822-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-115">Example</span></span>  
 <span data-ttu-id="60822-116">Nell'esempio seguente vengono ordinati gli ordini da `EmployeeID 1` in base al paese di spedizione, quindi in base al costo di spedizione dal più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="60822-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="60822-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="60822-117">Example</span></span>  
 <span data-ttu-id="60822-118">Nell'esempio seguente vengono combinati gli operatori <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> e <xref:System.Linq.Enumerable.GroupBy%2A> per trovare `Products` con il prezzo unitario più alto in ciascuna categoria, quindi per ordinare il gruppo in base all'ID della categoria.</span><span class="sxs-lookup"><span data-stu-id="60822-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="60822-119">Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="60822-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="60822-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60822-120">See Also</span></span>  
 [<span data-ttu-id="60822-121">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="60822-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="60822-122">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="60822-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
