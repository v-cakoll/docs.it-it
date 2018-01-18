---
title: Trovare il valore massimo in una sequenza numerica
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
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 028a8e4a7fa215b0bdbce1de92c20dc51a15faa6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="a01dc-102">Trovare il valore massimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="a01dc-102">Find the Maximum Value in a Numeric Sequence</span></span>
<span data-ttu-id="a01dc-103">Per trovare il valore massimo in una sequenza di valori numerici, usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="a01dc-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a01dc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a01dc-104">Example</span></span>  
 <span data-ttu-id="a01dc-105">Nell'esempio seguente viene cercata l'ultima data di assunzione di qualsiasi dipendente.</span><span class="sxs-lookup"><span data-stu-id="a01dc-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="a01dc-106">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="a01dc-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="a01dc-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a01dc-107">Example</span></span>  
 <span data-ttu-id="a01dc-108">Nell'esempio seguente viene cercato il maggior numero di unità in magazzino per qualsiasi prodotto.</span><span class="sxs-lookup"><span data-stu-id="a01dc-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="a01dc-109">Se si esegue questa query sul database di esempio Northwind, l'output sarà: `125`.</span><span class="sxs-lookup"><span data-stu-id="a01dc-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="a01dc-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a01dc-110">Example</span></span>  
 <span data-ttu-id="a01dc-111">Nell'esempio seguente viene usato Max per cercare in `Products` gli elementi con il prezzo unitario più elevato di ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="a01dc-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="a01dc-112">Nell'output vengono quindi elencati i risultati per categoria.</span><span class="sxs-lookup"><span data-stu-id="a01dc-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="a01dc-113">Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="a01dc-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a01dc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a01dc-114">See Also</span></span>  
 [<span data-ttu-id="a01dc-115">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="a01dc-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="a01dc-116">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="a01dc-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
