---
title: Trovare il valore massimo in una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: ebef8cb373da4021fd68fd7ce38de8cb06eb81ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782180"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="bd1a2-102">Trovare il valore massimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="bd1a2-102">Find the Maximum Value in a Numeric Sequence</span></span>
<span data-ttu-id="bd1a2-103">Per trovare il valore massimo in una sequenza di valori numerici, usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd1a2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd1a2-104">Example</span></span>  
 <span data-ttu-id="bd1a2-105">Nell'esempio seguente viene cercata l'ultima data di assunzione di qualsiasi dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="bd1a2-106">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="bd1a2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd1a2-107">Example</span></span>  
 <span data-ttu-id="bd1a2-108">Nell'esempio seguente viene cercato il maggior numero di unità in magazzino per qualsiasi prodotto.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="bd1a2-109">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `125`.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="bd1a2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd1a2-110">Example</span></span>  
 <span data-ttu-id="bd1a2-111">Nell'esempio seguente viene usato Max per cercare in `Products` gli elementi con il prezzo unitario più elevato di ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="bd1a2-112">Nell'output vengono quindi elencati i risultati per categoria.</span><span class="sxs-lookup"><span data-stu-id="bd1a2-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="bd1a2-113">Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd1a2-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd1a2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd1a2-114">See also</span></span>

- [<span data-ttu-id="bd1a2-115">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="bd1a2-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="bd1a2-116">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="bd1a2-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
