---
title: into - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: f0f5ff1e56a65e83385f814df2fadd957f53561e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713631"
---
# <a name="into-c-reference"></a><span data-ttu-id="f9aed-102">into (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f9aed-102">into (C# Reference)</span></span>

<span data-ttu-id="f9aed-103">La parola chiave contestuale `into` può essere usata per creare un identificatore temporaneo al fine di archiviare i risultati di una clausola [group](group-clause.md), [join](join-clause.md) o [select](select-clause.md) in un nuovo identificatore.</span><span class="sxs-lookup"><span data-stu-id="f9aed-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="f9aed-104">Questo identificatore può essere un generatore per altri comandi di query.</span><span class="sxs-lookup"><span data-stu-id="f9aed-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="f9aed-105">Se usato in una clausola `group` o `select`, l'utilizzo del nuovo identificatore viene talvolta definito *continuazione*.</span><span class="sxs-lookup"><span data-stu-id="f9aed-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="f9aed-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9aed-106">Example</span></span>

<span data-ttu-id="f9aed-107">Nell'esempio seguente viene illustrato l'utilizzo della parola chiave `into` per attivare un identificatore temporaneo `fruitGroup` che contiene un tipo dedotto di `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="f9aed-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="f9aed-108">Usando l'identificatore, è possibile richiamare il metodo <xref:System.Linq.Enumerable.Count%2A> su ogni gruppo e selezionare solo i gruppi che contengono due o più parole.</span><span class="sxs-lookup"><span data-stu-id="f9aed-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="f9aed-109">L'utilizzo di `into` in una clausola `group` è necessario solo quando si vuole eseguire operazioni di query aggiuntive in ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="f9aed-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="f9aed-110">Per altre informazioni, vedere [Clausola group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f9aed-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="f9aed-111">Per un esempio di utilizzo di `into` in una clausola `join`, vedere [Clausola join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f9aed-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9aed-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9aed-112">See also</span></span>

- [<span data-ttu-id="f9aed-113">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="f9aed-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="f9aed-114">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="f9aed-114">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="f9aed-115">Clausola group</span><span class="sxs-lookup"><span data-stu-id="f9aed-115">group clause</span></span>](group-clause.md)
