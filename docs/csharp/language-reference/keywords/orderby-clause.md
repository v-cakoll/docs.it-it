---
title: Clausola orderby (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="916bf-102">Clausola orderby (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="916bf-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="916bf-103">In un'espressione di query, la clausola `orderby` fa in modo che la sequenza o la sottosequenza (gruppo) restituita venga ordinata in modo crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="916bf-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="916bf-104">È possibile specificare più chiavi per eseguire una o più operazioni di ordinamento secondarie.</span><span class="sxs-lookup"><span data-stu-id="916bf-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="916bf-105">L'ordinamento viene eseguito dall'operatore di confronto predefinito per il tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="916bf-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="916bf-106">L'ordinamento predefinito è crescente.</span><span class="sxs-lookup"><span data-stu-id="916bf-106">The default sort order is ascending.</span></span> <span data-ttu-id="916bf-107">È possibile specificare anche un operatore di confronto personalizzato,</span><span class="sxs-lookup"><span data-stu-id="916bf-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="916bf-108">che sarà tuttavia disponibile solo se si usa la sintassi basata sul metodo.</span><span class="sxs-lookup"><span data-stu-id="916bf-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="916bf-109">Per altre informazioni, vedere [Ordinamento dei dati](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span><span class="sxs-lookup"><span data-stu-id="916bf-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="916bf-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="916bf-110">Example</span></span>  
 <span data-ttu-id="916bf-111">Nell'esempio seguente, la prima query ordina le parole alfabeticamente a partire da A, la seconda ordina le stesse parole in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="916bf-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="916bf-112">La parola chiave `ascending` è il valore di ordinamento predefinito e può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="916bf-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="916bf-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="916bf-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="916bf-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="916bf-114">Example</span></span>  
 <span data-ttu-id="916bf-115">Nell'esempio seguente viene eseguito un ordinamento primario sui cognomi degli studenti e quindi un ordinamento secondario sui nomi.</span><span class="sxs-lookup"><span data-stu-id="916bf-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="916bf-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="916bf-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="916bf-117">Note</span><span class="sxs-lookup"><span data-stu-id="916bf-117">Remarks</span></span>  
 <span data-ttu-id="916bf-118">In fase di compilazione, la clausola `orderby` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="916bf-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="916bf-119">Eventuali chiavi multiple nella clausola `orderby` vengono convertite in chiamate al metodo <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="916bf-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916bf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="916bf-120">See Also</span></span>  
 <span data-ttu-id="916bf-121">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="916bf-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="916bf-122">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="916bf-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="916bf-123">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="916bf-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="916bf-124">[Clausola group](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="916bf-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="916bf-125">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="916bf-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

