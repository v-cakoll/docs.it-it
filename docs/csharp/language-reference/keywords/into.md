---
title: into (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
dev_langs:
- CSharp
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
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
ms.openlocfilehash: ef85caf02387432761e5ccbb7e0478b46d32f795
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="into-c-reference"></a><span data-ttu-id="e8825-102">into (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e8825-102">into (C# Reference)</span></span>
<span data-ttu-id="e8825-103">La parola chiave contestuale `into` può essere usata per creare un identificatore temporaneo al fine di archiviare i risultati di una clausola [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) o [select](../../../csharp/language-reference/keywords/select-clause.md) in un nuovo identificatore.</span><span class="sxs-lookup"><span data-stu-id="e8825-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) or [select](../../../csharp/language-reference/keywords/select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="e8825-104">Questo identificatore può essere un generatore per altri comandi di query.</span><span class="sxs-lookup"><span data-stu-id="e8825-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="e8825-105">Se usato in una clausola `group` o `select`, l'utilizzo del nuovo identificatore viene talvolta definito *continuazione*.</span><span class="sxs-lookup"><span data-stu-id="e8825-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8825-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8825-106">Example</span></span>  
 <span data-ttu-id="e8825-107">Nell'esempio seguente viene illustrato l'utilizzo della parola chiave `into` per attivare un identificatore temporaneo `fruitGroup` che contiene un tipo dedotto di `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="e8825-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="e8825-108">Usando l'identificatore, è possibile richiamare il metodo <xref:System.Linq.Enumerable.Count%2A> su ogni gruppo e selezionare solo i gruppi che contengono due o più parole.</span><span class="sxs-lookup"><span data-stu-id="e8825-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>  
  
 <span data-ttu-id="e8825-109">[!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8825-109">[!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]</span></span>  
  
 <span data-ttu-id="e8825-110">L'utilizzo di `into` in una clausola `group` è necessario solo quando si vuole eseguire operazioni di query aggiuntive in ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="e8825-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="e8825-111">Per altre informazioni, vedere [Clausola group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e8825-111">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="e8825-112">Per un esempio di utilizzo di `into` in una clausola `join`, vedere [Clausola join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e8825-112">For an example of the use of `into` in a `join` clause, see [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8825-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8825-113">See Also</span></span>  
 <span data-ttu-id="e8825-114">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e8825-114">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="e8825-115">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8825-115">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="e8825-116">Clausola group</span><span class="sxs-lookup"><span data-stu-id="e8825-116">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)

