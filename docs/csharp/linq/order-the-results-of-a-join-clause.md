---
title: Ordinare i risultati di una clausola join (LINQ in C#)
description: Informazioni su come ordinare i risultati di una clausola join LINQ in C#.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659865"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="dc172-103">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="dc172-103">Order the results of a join clause</span></span>

<span data-ttu-id="dc172-104">Questo esempio descrive come ordinare i risultati di un'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="dc172-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="dc172-105">Si noti che l'ordinamento viene eseguito dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="dc172-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="dc172-106">In genere, sebbene sia possibile, non è consigliabile usare una clausola `orderby` con una o più sequenze di origine prima dell'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="dc172-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="dc172-107">Alcuni provider LINQ potrebbero non mantenere tale ordinamento dopo l'operazione di join.</span><span class="sxs-lookup"><span data-stu-id="dc172-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="dc172-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc172-108">Example</span></span>

<span data-ttu-id="dc172-109">Questa query crea un join di gruppo e quindi ordina i gruppi in base all'elemento categoria che è ancora nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="dc172-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="dc172-110">Nell'inizializzatore di tipi anonimi una sottoquery ordina tutti gli elementi corrispondenti della sequenza di prodotti.</span><span class="sxs-lookup"><span data-stu-id="dc172-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="dc172-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc172-111">See also</span></span>

- [<span data-ttu-id="dc172-112">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="dc172-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="dc172-113">Clausola orderby</span><span class="sxs-lookup"><span data-stu-id="dc172-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="dc172-114">clausola join</span><span class="sxs-lookup"><span data-stu-id="dc172-114">join clause</span></span>](../language-reference/keywords/join-clause.md)
