---
title: Ordinare i risultati di una clausola join
description: Come ordinare i risultati di una clausola join.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="18abb-104">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="18abb-104">Order the results of a join clause</span></span>
<span data-ttu-id="18abb-105">Questo esempio descrive come ordinare i risultati di un'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="18abb-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="18abb-106">Si noti che l'ordinamento viene eseguito dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="18abb-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="18abb-107">In genere, sebbene sia possibile, non è consigliabile usare una clausola `orderby` con una o più sequenze di origine prima dell'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="18abb-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="18abb-108">Alcuni provider LINQ potrebbero non mantenere tale ordinamento dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="18abb-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18abb-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="18abb-109">Example</span></span>  
 <span data-ttu-id="18abb-110">Questa query crea un join di gruppo e quindi ordina i gruppi in base all'elemento categoria che è ancora nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="18abb-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="18abb-111">Nell'inizializzatore di tipi anonimi una sottoquery ordina tutti gli elementi corrispondenti della sequenza di prodotti.</span><span class="sxs-lookup"><span data-stu-id="18abb-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="18abb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18abb-112">See also</span></span>  
 [<span data-ttu-id="18abb-113">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="18abb-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="18abb-114">Clausola orderby</span><span class="sxs-lookup"><span data-stu-id="18abb-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="18abb-115">Clausola join</span><span class="sxs-lookup"><span data-stu-id="18abb-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 
