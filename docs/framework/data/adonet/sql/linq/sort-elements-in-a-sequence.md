---
title: Ordinare elementi in una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 8f645232d2ae9d9bad8c26a5b9fec2243c6cf9d0
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380017"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="ac20a-102">Ordinare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="ac20a-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="ac20a-103">Usare l'operatore <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare una sequenza in base a una o più chiavi.</span><span class="sxs-lookup"><span data-stu-id="ac20a-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ac20a-104">è progettato per supportare l'ordinamento in base a semplici tipi primitivi, ad esempio `string`, `int`e così via.</span><span class="sxs-lookup"><span data-stu-id="ac20a-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="ac20a-105">Non supporta invece l'ordinamento per classi multivalore complesse, ad esempio i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="ac20a-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="ac20a-106">Non supporta inoltre i tipi di dati `byte`.</span><span class="sxs-lookup"><span data-stu-id="ac20a-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac20a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-107">Example</span></span>  
 <span data-ttu-id="ac20a-108">Nell'esempio seguente vengono ordinati `Employees` in base alla data di assunzione.</span><span class="sxs-lookup"><span data-stu-id="ac20a-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="ac20a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-109">Example</span></span>  
 <span data-ttu-id="ac20a-110">Nell'esempio seguente viene usato `where` per l'ordinamento di `Orders` spediti a `London` in base al costo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="ac20a-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="ac20a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-111">Example</span></span>  
 <span data-ttu-id="ac20a-112">Nell'esempio seguente vengono ordinati `Products` in base al prezzo unitario dal più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="ac20a-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="ac20a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-113">Example</span></span>  
 <span data-ttu-id="ac20a-114">Nell'esempio seguente viene usato il tipo `OrderBy` composto per ordinare `Customers` in base alla città, quindi al nome del contatto.</span><span class="sxs-lookup"><span data-stu-id="ac20a-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="ac20a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-115">Example</span></span>  
 <span data-ttu-id="ac20a-116">Nell'esempio seguente vengono ordinati gli ordini dal `EmployeeID 1` da `ShipCountry`e quindi dal più alto al più basso costo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="ac20a-116">The following example sorts Orders from `EmployeeID 1` by `ShipCountry`, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="ac20a-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-117">Example</span></span>  
 <span data-ttu-id="ac20a-118">Nell'esempio seguente vengono combinati gli operatori <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> e <xref:System.Linq.Enumerable.GroupBy%2A> per trovare `Products` con il prezzo unitario più alto in ciascuna categoria, quindi per ordinare il gruppo in base all'ID della categoria.</span><span class="sxs-lookup"><span data-stu-id="ac20a-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="ac20a-119">Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac20a-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac20a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac20a-120">See also</span></span>

- [<span data-ttu-id="ac20a-121">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="ac20a-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="ac20a-122">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="ac20a-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
