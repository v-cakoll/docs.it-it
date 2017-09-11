---
title: Query (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic]
- LINQ, queries
ms.assetid: 8edc717c-4a24-4cbc-9c16-11f479c935db
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a178714055076537033fbda32d7c7c1c544351d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="queries-visual-basic"></a><span data-ttu-id="4885f-102">Query (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4885f-102">Queries (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4885f-103">Consente di creare [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] espressioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="4885f-103"> enables you to create [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4885f-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4885f-104">In This Section</span></span>  
 [<span data-ttu-id="4885f-105">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="4885f-105">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 <span data-ttu-id="4885f-106">Viene descritto il `Aggregate` clausola, che applica uno o più funzioni di aggregazione a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="4885f-106">Describes the `Aggregate` clause, which applies one or more aggregate functions to a collection.</span></span>  
  
 [<span data-ttu-id="4885f-107">Clausola Distinct</span><span class="sxs-lookup"><span data-stu-id="4885f-107">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 <span data-ttu-id="4885f-108">Viene descritto il `Distinct` clausola che limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="4885f-108">Describes the `Distinct` clause, which restricts the values of the current range variable to eliminate duplicate values in query results.</span></span>  
  
 [<span data-ttu-id="4885f-109">Clausola From</span><span class="sxs-lookup"><span data-stu-id="4885f-109">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 <span data-ttu-id="4885f-110">Viene descritto il `From` clausola che specifica una raccolta e una variabile di intervallo per una query.</span><span class="sxs-lookup"><span data-stu-id="4885f-110">Describes the `From` clause, which specifies a collection and a range variable for a query.</span></span>  
  
 [<span data-ttu-id="4885f-111">Clausola Group By</span><span class="sxs-lookup"><span data-stu-id="4885f-111">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)  
 <span data-ttu-id="4885f-112">Viene descritto il `Group By` clausola, che raggruppa gli elementi del risultato della query e può essere utilizzato per applicare le funzioni di aggregazione a ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="4885f-112">Describes the `Group By` clause, which groups the elements of a query result and can be used to apply aggregate functions to each group.</span></span>  
  
 [<span data-ttu-id="4885f-113">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="4885f-113">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 <span data-ttu-id="4885f-114">Viene descritto il `Group Join` clausola, che combina due raccolte in un'unica raccolta gerarchica.</span><span class="sxs-lookup"><span data-stu-id="4885f-114">Describes the `Group Join` clause, which combines two collections into a single hierarchical collection.</span></span>  
  
 [<span data-ttu-id="4885f-115">Clausola Join</span><span class="sxs-lookup"><span data-stu-id="4885f-115">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 <span data-ttu-id="4885f-116">Viene descritto il `Join` clausola, che combina due raccolte in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="4885f-116">Describes the `Join` clause, which combines two collections into a single collection.</span></span>  
  
 [<span data-ttu-id="4885f-117">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="4885f-117">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 <span data-ttu-id="4885f-118">Viene descritto il `Let` clausola, che calcola un valore e lo assegna a una nuova variabile nella query.</span><span class="sxs-lookup"><span data-stu-id="4885f-118">Describes the `Let` clause, which computes a value and assigns it to a new variable in the query.</span></span>  
  
 [<span data-ttu-id="4885f-119">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="4885f-119">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 <span data-ttu-id="4885f-120">Viene descritto il `Order By` clausola che specifica l'ordinamento per le colonne in una query.</span><span class="sxs-lookup"><span data-stu-id="4885f-120">Describes the `Order By` clause, which specifies the sort order for columns in a query.</span></span>  
  
 [<span data-ttu-id="4885f-121">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="4885f-121">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 <span data-ttu-id="4885f-122">Viene descritto il `Select` clausola, che dichiara una serie di variabili di intervallo per una query.</span><span class="sxs-lookup"><span data-stu-id="4885f-122">Describes the `Select` clause, which declares a set of range variables for a query.</span></span>  
  
 [<span data-ttu-id="4885f-123">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="4885f-123">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 <span data-ttu-id="4885f-124">Viene descritto il `Skip` clausola, che ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="4885f-124">Describes the `Skip` clause, which bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="4885f-125">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="4885f-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 <span data-ttu-id="4885f-126">Viene descritto il `Skip While` clausola, che ignora gli elementi in una raccolta, purché una condizione specificata sia `true` e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="4885f-126">Describes the `Skip While` clause, which bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="4885f-127">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="4885f-127">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 <span data-ttu-id="4885f-128">Viene descritto il `Take` clausola, che restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="4885f-128">Describes the `Take` clause, which returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
 [<span data-ttu-id="4885f-129">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="4885f-129">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 <span data-ttu-id="4885f-130">Viene descritto il `Take While` clausola, che include gli elementi in una raccolta, purché una condizione specificata sia `true` e ignora gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="4885f-130">Describes the `Take While` clause, which includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
 [<span data-ttu-id="4885f-131">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="4885f-131">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="4885f-132">Viene descritto il `Where` clausola che specifica una condizione di filtro per una query.</span><span class="sxs-lookup"><span data-stu-id="4885f-132">Describes the `Where` clause, which specifies a filtering condition for a query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4885f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4885f-133">See Also</span></span>  
 <span data-ttu-id="4885f-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="4885f-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="4885f-135"> [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="4885f-135"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
