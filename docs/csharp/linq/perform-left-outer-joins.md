---
title: Eseguire left outer join
description: Come eseguire i left outer join.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d81f6e9df228dc6eec985253f53b70a95493ed42
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="b355d-104">Eseguire left outer join</span><span class="sxs-lookup"><span data-stu-id="b355d-104">Perform left outer joins</span></span>
<span data-ttu-id="b355d-105">Un left outer join è un join in cui viene restituito ogni elemento della prima raccolta, anche se non ha elementi correlati nella seconda raccolta.</span><span class="sxs-lookup"><span data-stu-id="b355d-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="b355d-106">È possibile usare LINQ per eseguire un left outer join chiamando il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b355d-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b355d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b355d-107">Example</span></span>  
 <span data-ttu-id="b355d-108">L'esempio seguente illustra come usare il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo per eseguire un left outer join.</span><span class="sxs-lookup"><span data-stu-id="b355d-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="b355d-109">Il primo passaggio nella produzione di un left outer join di due raccolte consiste nell'esecuzione di un inner join usando un join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b355d-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="b355d-110">Per una descrizione di questo processo, vedere [Eseguire inner join](perform-inner-joins.md). In questo esempio l'elenco di oggetti `Person` è unito tramite inner join all'elenco di oggetti `Pet` basati su un oggetto `Person` che corrisponde a `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="b355d-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="b355d-111">Il secondo passaggio consiste nell'includere ogni elemento della prima raccolta di sinistra nel set di risultati anche se l'elemento non ha corrispondenze nella raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="b355d-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="b355d-112">Questa operazione viene eseguita chiamando <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> in ogni sequenza di elementi corrispondenti dal join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b355d-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="b355d-113">In questo esempio <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> viene chiamato in ogni sequenza di oggetti `Pet` corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b355d-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="b355d-114">Il metodo restituisce una raccolta che contiene un solo valore predefinito se la sequenza di oggetti `Pet` corrispondenti è vuota per qualsiasi oggetto `Person`, assicurando in questo modo che ogni oggetto `Person` sia rappresentato nella raccolta di risultati.</span><span class="sxs-lookup"><span data-stu-id="b355d-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b355d-115">Il valore predefinito per un tipo di riferimento è `null`. Di conseguenza, l'esempio cerca un riferimento Null prima di accedere a ogni elemento di ogni raccolta `Pet`.</span><span class="sxs-lookup"><span data-stu-id="b355d-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 <span data-ttu-id="b355d-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b355d-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="b355d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b355d-117">See also</span></span>  
 <span data-ttu-id="b355d-118"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="b355d-118"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="b355d-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="b355d-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="b355d-120">[Eseguire inner join](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="b355d-120">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="b355d-121">[Eseguire join raggruppati](perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="b355d-121">[Perform grouped joins](perform-grouped-joins.md) </span></span>  
 [<span data-ttu-id="b355d-122">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="b355d-122">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)   
 

