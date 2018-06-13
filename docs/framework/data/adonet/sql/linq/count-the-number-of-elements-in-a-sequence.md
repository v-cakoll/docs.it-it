---
title: Contare il numero di elementi in una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 928cfd33a187637c6d18da3cccefb22bb2950acf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353836"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="15f02-102">Contare il numero di elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="15f02-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="15f02-103">Usare l'operatore <xref:System.Linq.Enumerable.Count%2A> per conteggiare il numero di elementi in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="15f02-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="15f02-104">L'esecuzione di questa query sul database di esempio Northwind produce un output pari a `91`.</span><span class="sxs-lookup"><span data-stu-id="15f02-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15f02-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="15f02-105">Example</span></span>  
 <span data-ttu-id="15f02-106">Nell'esempio riportato di seguito viene conteggiato il numero di `Customers` nel database.</span><span class="sxs-lookup"><span data-stu-id="15f02-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="15f02-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="15f02-107">Example</span></span>  
 <span data-ttu-id="15f02-108">Nell'esempio seguente viene conteggiato il numero di prodotti nel database che non sono stati rimossi.</span><span class="sxs-lookup"><span data-stu-id="15f02-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="15f02-109">L'esecuzione di questo esempio sul database di esempio Northwind produce un output pari a `69`.</span><span class="sxs-lookup"><span data-stu-id="15f02-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="15f02-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f02-110">See Also</span></span>  
 [<span data-ttu-id="15f02-111">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="15f02-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="15f02-112">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="15f02-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
