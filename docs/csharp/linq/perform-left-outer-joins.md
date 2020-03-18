---
title: Eseguire left outer join (LINQ in C#)
description: Informazioni su come eseguire left outer join usando LINQ in C#.
ms.date: 12/01/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: cc08a1c8670623a10d1e0bf10221d02037a8d7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688579"
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="10eb9-103">Eseguire left outer join</span><span class="sxs-lookup"><span data-stu-id="10eb9-103">Perform left outer joins</span></span>

<span data-ttu-id="10eb9-104">Un left outer join è un join in cui viene restituito ogni elemento della prima raccolta, anche se non ha elementi correlati nella seconda raccolta.</span><span class="sxs-lookup"><span data-stu-id="10eb9-104">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="10eb9-105">È possibile usare LINQ per eseguire un left outer join chiamando il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="10eb9-105">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>

## <a name="example"></a><span data-ttu-id="10eb9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="10eb9-106">Example</span></span>

<span data-ttu-id="10eb9-107">L'esempio seguente illustra come usare il metodo <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> nei risultati di un join di gruppo per eseguire un left outer join.</span><span class="sxs-lookup"><span data-stu-id="10eb9-107">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>

<span data-ttu-id="10eb9-108">Il primo passaggio nella produzione di un left outer join di due raccolte consiste nell'esecuzione di un inner join usando un join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="10eb9-108">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="10eb9-109">Per una spiegazione di questo processo, vedere [Eseguire inner join.](perform-inner-joins.md) In questo esempio, `Person` l'elenco di oggetti è `Pet` unito in `Person` join `Pet.Owner`interno all'elenco di oggetti in base a un oggetto che corrisponde a .</span><span class="sxs-lookup"><span data-stu-id="10eb9-109">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>

<span data-ttu-id="10eb9-110">Il secondo passaggio consiste nell'includere ogni elemento della prima raccolta di sinistra nel set di risultati anche se l'elemento non ha corrispondenze nella raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="10eb9-110">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="10eb9-111">Questa operazione viene eseguita chiamando <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> in ogni sequenza di elementi corrispondenti dal join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="10eb9-111">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="10eb9-112">In questo esempio <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> viene chiamato in ogni sequenza di oggetti `Pet` corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="10eb9-112">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="10eb9-113">Il metodo restituisce una raccolta che contiene un solo valore predefinito se la sequenza di oggetti `Pet` corrispondenti è vuota per qualsiasi oggetto `Person`, assicurando in questo modo che ogni oggetto `Person` sia rappresentato nella raccolta di risultati.</span><span class="sxs-lookup"><span data-stu-id="10eb9-113">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>

> [!NOTE]
> <span data-ttu-id="10eb9-114">Il valore predefinito per un tipo di riferimento è `null`. Di conseguenza, l'esempio cerca un riferimento Null prima di accedere a ogni elemento di ogni raccolta `Pet`.</span><span class="sxs-lookup"><span data-stu-id="10eb9-114">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a><span data-ttu-id="10eb9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10eb9-115">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [<span data-ttu-id="10eb9-116">Eseguire inner join</span><span class="sxs-lookup"><span data-stu-id="10eb9-116">Perform inner joins</span></span>](perform-inner-joins.md)
- [<span data-ttu-id="10eb9-117">Eseguire join raggruppati</span><span class="sxs-lookup"><span data-stu-id="10eb9-117">Perform grouped joins</span></span>](perform-grouped-joins.md)
- [<span data-ttu-id="10eb9-118">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="10eb9-118">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
