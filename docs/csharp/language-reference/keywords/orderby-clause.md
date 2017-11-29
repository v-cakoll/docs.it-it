---
title: Clausola orderby (Riferimento C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc688e7ba164dcca71d13b2d79d30f1373c4778e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="d14b0-102">Clausola orderby (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="d14b0-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="d14b0-103">In un'espressione di query, la clausola `orderby` fa in modo che la sequenza o la sottosequenza (gruppo) restituita venga ordinata in modo crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="d14b0-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="d14b0-104">È possibile specificare più chiavi per eseguire una o più operazioni di ordinamento secondarie.</span><span class="sxs-lookup"><span data-stu-id="d14b0-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="d14b0-105">L'ordinamento viene eseguito dall'operatore di confronto predefinito per il tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d14b0-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="d14b0-106">L'ordinamento predefinito è crescente.</span><span class="sxs-lookup"><span data-stu-id="d14b0-106">The default sort order is ascending.</span></span> <span data-ttu-id="d14b0-107">È possibile specificare anche un operatore di confronto personalizzato,</span><span class="sxs-lookup"><span data-stu-id="d14b0-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="d14b0-108">che sarà tuttavia disponibile solo se si usa la sintassi basata sul metodo.</span><span class="sxs-lookup"><span data-stu-id="d14b0-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="d14b0-109">Per altre informazioni, vedere [Ordinamento dei dati](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="d14b0-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d14b0-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d14b0-110">Example</span></span>  
 <span data-ttu-id="d14b0-111">Nell'esempio seguente, la prima query ordina le parole alfabeticamente a partire da A, la seconda ordina le stesse parole in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="d14b0-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="d14b0-112">La parola chiave `ascending` è il valore di ordinamento predefinito e può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="d14b0-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d14b0-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d14b0-113">Example</span></span>  
 <span data-ttu-id="d14b0-114">Nell'esempio seguente viene eseguito un ordinamento primario sui cognomi degli studenti e quindi un ordinamento secondario sui nomi.</span><span class="sxs-lookup"><span data-stu-id="d14b0-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="d14b0-115">Note</span><span class="sxs-lookup"><span data-stu-id="d14b0-115">Remarks</span></span>  
 <span data-ttu-id="d14b0-116">In fase di compilazione, la clausola `orderby` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="d14b0-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="d14b0-117">Eventuali chiavi multiple nella clausola `orderby` vengono convertite in chiamate al metodo <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="d14b0-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14b0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14b0-118">See Also</span></span>  
 [<span data-ttu-id="d14b0-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d14b0-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d14b0-120">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d14b0-120">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="d14b0-121">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="d14b0-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="d14b0-122">Clausola group</span><span class="sxs-lookup"><span data-stu-id="d14b0-122">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="d14b0-123">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="d14b0-123">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
