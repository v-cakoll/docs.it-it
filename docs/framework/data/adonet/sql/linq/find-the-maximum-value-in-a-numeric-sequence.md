---
title: Trovare il valore massimo in una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: c93b322c755036c8bf7150bb5c96b9c32b6dc9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353817"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="2b277-102">Trovare il valore massimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="2b277-102">Find the Maximum Value in a Numeric Sequence</span></span>
<span data-ttu-id="2b277-103">Per trovare il valore massimo in una sequenza di valori numerici, usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b277-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b277-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b277-104">Example</span></span>  
 <span data-ttu-id="2b277-105">Nell'esempio seguente viene cercata l'ultima data di assunzione di qualsiasi dipendente.</span><span class="sxs-lookup"><span data-stu-id="2b277-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="2b277-106">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="2b277-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="2b277-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b277-107">Example</span></span>  
 <span data-ttu-id="2b277-108">Nell'esempio seguente viene cercato il maggior numero di unità in magazzino per qualsiasi prodotto.</span><span class="sxs-lookup"><span data-stu-id="2b277-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="2b277-109">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `125`.</span><span class="sxs-lookup"><span data-stu-id="2b277-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="2b277-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b277-110">Example</span></span>  
 <span data-ttu-id="2b277-111">Nell'esempio seguente viene usato Max per cercare in `Products` gli elementi con il prezzo unitario più elevato di ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="2b277-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="2b277-112">Nell'output vengono quindi elencati i risultati per categoria.</span><span class="sxs-lookup"><span data-stu-id="2b277-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="2b277-113">Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b277-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b277-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b277-114">See Also</span></span>  
 [<span data-ttu-id="2b277-115">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="2b277-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="2b277-116">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="2b277-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
