---
title: Eseguire una sottoquery su un'operazione di raggruppamento
description: Come eseguire una sottoquery su un'operazione di raggruppamento.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: f638b8a679a15891d04e02f1597d6bf7934a9e74
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="f0c2b-104">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f0c2b-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="f0c2b-105">Questo argomento descrive due diversi modi per creare una query che ordina i dati di origine in gruppi e quindi esegue una sottoquery separatamente su ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="f0c2b-106">La tecnica di base in ogni esempio consiste nel raggruppare gli elementi di origine usando una *continuazione* denominata `newGroup` e quindi generando una nuova sottoquery su `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="f0c2b-107">La sottoquery viene eseguita su ogni nuovo gruppo creato dalla query esterna.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="f0c2b-108">Si noti che in questo esempio l'output finale non è un gruppo, ma una sequenza semplice di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="f0c2b-109">Per altre informazioni sul raggruppamento, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2b-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="f0c2b-110">Per altre informazioni sulle continuazioni, vedere [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2b-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="f0c2b-111">L'esempio seguente usa una struttura dati in memoria come origine dati, ma gli stessi principi si applicano a qualsiasi tipo di origine dati LINQ.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c2b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0c2b-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="f0c2b-113">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2b-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a><span data-ttu-id="f0c2b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0c2b-114">See also</span></span>  
 [<span data-ttu-id="f0c2b-115">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="f0c2b-115">LINQ Query Expressions</span></span>](index.md)
