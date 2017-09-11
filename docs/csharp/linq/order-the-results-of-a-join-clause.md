---
title: Ordinare i risultati di una clausola join
description: Come ordinare i risultati di una clausola join.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6272181647bb200c18231c5fc836e3dd1a2d6d55
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="41c1d-104">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="41c1d-104">Order the results of a join clause</span></span>
<span data-ttu-id="41c1d-105">Questo esempio descrive come ordinare i risultati di un'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="41c1d-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="41c1d-106">Si noti che l'ordinamento viene eseguito dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="41c1d-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="41c1d-107">In genere, sebbene sia possibile, non è consigliabile usare una clausola `orderby` con una o più sequenze di origine prima dell'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="41c1d-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="41c1d-108">Alcuni provider LINQ potrebbero non mantenere tale ordinamento dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="41c1d-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41c1d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="41c1d-109">Example</span></span>  
 <span data-ttu-id="41c1d-110">Questa query crea un join di gruppo e quindi ordina i gruppi in base all'elemento categoria che è ancora nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="41c1d-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="41c1d-111">Nell'inizializzatore di tipi anonimi una sottoquery ordina tutti gli elementi corrispondenti della sequenza di prodotti.</span><span class="sxs-lookup"><span data-stu-id="41c1d-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 <span data-ttu-id="41c1d-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41c1d-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="41c1d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41c1d-113">See also</span></span>  
 <span data-ttu-id="41c1d-114">[Espressioni di query LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="41c1d-114">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="41c1d-115">[Clausola orderby](../language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="41c1d-115">[orderby clause](../language-reference/keywords/orderby-clause.md) </span></span>  
 [<span data-ttu-id="41c1d-116">Clausola join</span><span class="sxs-lookup"><span data-stu-id="41c1d-116">join clause</span></span>](../language-reference/keywords/join-clause.md) 

