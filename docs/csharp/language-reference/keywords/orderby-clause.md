---
title: Clausola orderby (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: cd76b2c33fe1a1a986bc05e3c3ed5f22809686ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173575"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="86c19-102">Clausola orderby (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="86c19-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="86c19-103">In un'espressione di query, la clausola `orderby` fa in modo che la sequenza o la sottosequenza (gruppo) restituita venga ordinata in modo crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="86c19-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="86c19-104">È possibile specificare più chiavi per eseguire una o più operazioni di ordinamento secondarie.</span><span class="sxs-lookup"><span data-stu-id="86c19-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="86c19-105">L'ordinamento viene eseguito dall'operatore di confronto predefinito per il tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="86c19-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="86c19-106">Per impostazione predefinita, l'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="86c19-106">The default sort order is ascending.</span></span> <span data-ttu-id="86c19-107">È possibile specificare anche un operatore di confronto personalizzato,</span><span class="sxs-lookup"><span data-stu-id="86c19-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="86c19-108">che sarà tuttavia disponibile solo se si usa la sintassi basata sul metodo.</span><span class="sxs-lookup"><span data-stu-id="86c19-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="86c19-109">Per altre informazioni, vedere [Ordinamento dei dati](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="86c19-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="86c19-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="86c19-110">Example</span></span>

<span data-ttu-id="86c19-111">Nell'esempio seguente, la prima query ordina le parole alfabeticamente a partire da A, la seconda ordina le stesse parole in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="86c19-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="86c19-112">La parola chiave `ascending` è il valore di ordinamento predefinito e può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="86c19-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="86c19-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="86c19-113">Example</span></span>

<span data-ttu-id="86c19-114">Nell'esempio seguente viene eseguito un ordinamento primario sui cognomi degli studenti e quindi un ordinamento secondario sui nomi.</span><span class="sxs-lookup"><span data-stu-id="86c19-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="86c19-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="86c19-115">Remarks</span></span>

<span data-ttu-id="86c19-116">In fase di compilazione, la clausola `orderby` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="86c19-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="86c19-117">Eventuali chiavi multiple nella clausola `orderby` vengono convertite in chiamate al metodo <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="86c19-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="86c19-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86c19-118">See also</span></span>

- [<span data-ttu-id="86c19-119">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="86c19-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="86c19-120">Parole chiave di query (LINQ)Query Keywords (LINQ)</span><span class="sxs-lookup"><span data-stu-id="86c19-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="86c19-121">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="86c19-121">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="86c19-122">Clausola group</span><span class="sxs-lookup"><span data-stu-id="86c19-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="86c19-123">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="86c19-123">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
