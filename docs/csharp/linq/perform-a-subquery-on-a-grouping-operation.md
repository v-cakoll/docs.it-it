---
title: Eseguire una sottoquery su un'operazione di raggruppamento (LINQ in C#)
description: Come eseguire una sottoquery su un'operazione di raggruppamento usando LINQ in C#.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 514db81b80557a3026589f00177910cc9446c0f4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213053"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="fa81a-103">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="fa81a-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="fa81a-104">Questo articolo descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="fa81a-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="fa81a-105">La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="fa81a-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="fa81a-106">La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna.</span><span class="sxs-lookup"><span data-stu-id="fa81a-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="fa81a-107">Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="fa81a-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="fa81a-108">Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fa81a-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="fa81a-109">Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="fa81a-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="fa81a-110">L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.</span><span class="sxs-lookup"><span data-stu-id="fa81a-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa81a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa81a-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="fa81a-112">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="fa81a-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="fa81a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa81a-113">See also</span></span>

- [<span data-ttu-id="fa81a-114">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="fa81a-114">Language Integrated Query (LINQ)</span></span>](index.md)
