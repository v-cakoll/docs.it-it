---
title: Eseguire una sottoquery su un'operazione di raggruppamento (LINQ in C#)
description: Come eseguire una sottoquery su un'operazione di raggruppamento usando LINQ in C#.
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: fd26f87ad7d5b4892f086bf8c7a34cf19a7f9e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173367"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="f07ae-103">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f07ae-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="f07ae-104">Questo articolo descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="f07ae-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="f07ae-105">La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="f07ae-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="f07ae-106">La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna.</span><span class="sxs-lookup"><span data-stu-id="f07ae-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="f07ae-107">Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="f07ae-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="f07ae-108">Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f07ae-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="f07ae-109">Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="f07ae-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="f07ae-110">L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.</span><span class="sxs-lookup"><span data-stu-id="f07ae-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f07ae-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f07ae-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="f07ae-112">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f07ae-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]

<span data-ttu-id="f07ae-113">La query nel frammento di codice precedente può essere scritta anche usando la sintassi del metodo.</span><span class="sxs-lookup"><span data-stu-id="f07ae-113">The query in the snippet above can also be written using method syntax.</span></span> <span data-ttu-id="f07ae-114">Il frammento di codice seguente è una query semanticamente equivalente scritta usando la sintassi del metodo.</span><span class="sxs-lookup"><span data-stu-id="f07ae-114">The following code snippet has a semantically equivalent query written using method syntax.</span></span>

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a><span data-ttu-id="f07ae-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f07ae-115">See also</span></span>

- [<span data-ttu-id="f07ae-116">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="f07ae-116">Language Integrated Query (LINQ)</span></span>](index.md)
