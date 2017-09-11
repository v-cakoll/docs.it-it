---
title: Eseguire una sottoquery su un'operazione di raggruppamento
description: Come eseguire una sottoquery su un'operazione di raggruppamento.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68acc07e0c33d042123d3cd403a73d58a7c3d245
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="39da6-104">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="39da6-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="39da6-105">Questo argomento descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="39da6-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="39da6-106">La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="39da6-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="39da6-107">La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna.</span><span class="sxs-lookup"><span data-stu-id="39da6-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="39da6-108">Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="39da6-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="39da6-109">Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="39da6-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="39da6-110">Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="39da6-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="39da6-111">L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.</span><span class="sxs-lookup"><span data-stu-id="39da6-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39da6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="39da6-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="39da6-113">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="39da6-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 <span data-ttu-id="39da6-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39da6-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span></span>  
   
## <a name="see-also"></a><span data-ttu-id="39da6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39da6-115">See also</span></span>  
 [<span data-ttu-id="39da6-116">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="39da6-116">LINQ Query Expressions</span></span>](index.md)

