---
title: Partizionamento dei dati (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d0df2bc473f48fba4bbb094317166407f7c7ec2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="01e8e-102">Partizionamento dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e8e-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="01e8e-103">Il partizionamento in LINQ si riferisce all'operazione di divisione di una sequenza di input in due sezioni, senza ridisporre gli elementi e restituendo quindi una delle sezioni.</span><span class="sxs-lookup"><span data-stu-id="01e8e-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="01e8e-104">Nella figura seguente mostra i risultati di tre diverse operazioni di partizionamento su una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="01e8e-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="01e8e-105">La prima operazione restituisce i primi tre elementi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="01e8e-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="01e8e-106">La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="01e8e-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="01e8e-107">La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.</span><span class="sxs-lookup"><span data-stu-id="01e8e-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="01e8e-108">![Operazioni di partizionamento LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="01e8e-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="01e8e-109">Nella sezione seguente sono elencati i metodi degli operatori query standard che le sequenze di partizione.</span><span class="sxs-lookup"><span data-stu-id="01e8e-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="01e8e-110">Operatori</span><span class="sxs-lookup"><span data-stu-id="01e8e-110">Operators</span></span>  
  
|<span data-ttu-id="01e8e-111">Nome dell'operatore</span><span class="sxs-lookup"><span data-stu-id="01e8e-111">Operator Name</span></span>|<span data-ttu-id="01e8e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01e8e-112">Description</span></span>|<span data-ttu-id="01e8e-113">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01e8e-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="01e8e-114">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="01e8e-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="01e8e-115">Skip</span><span class="sxs-lookup"><span data-stu-id="01e8e-115">Skip</span></span>|<span data-ttu-id="01e8e-116">Ignora gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="01e8e-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<span data-ttu-id="01e8e-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="01e8e-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="01e8e-119">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="01e8e-119">SkipWhile</span></span>|<span data-ttu-id="01e8e-120">Ignora gli elementi basati su una funzione predicativa finché un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="01e8e-120">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<span data-ttu-id="01e8e-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="01e8e-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="01e8e-123">Take</span><span class="sxs-lookup"><span data-stu-id="01e8e-123">Take</span></span>|<span data-ttu-id="01e8e-124">Accetta gli elementi fino a una posizione specificata in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="01e8e-124">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<span data-ttu-id="01e8e-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="01e8e-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="01e8e-127">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="01e8e-127">TakeWhile</span></span>|<span data-ttu-id="01e8e-128">Accetta gli elementi basati su una funzione predicativa finché un elemento non soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="01e8e-128">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<span data-ttu-id="01e8e-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="01e8e-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="01e8e-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="01e8e-131">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="01e8e-131">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="01e8e-132">Skip</span><span class="sxs-lookup"><span data-stu-id="01e8e-132">Skip</span></span>  
 <span data-ttu-id="01e8e-133">Nell'esempio di codice viene illustrato come utilizzare il `Skip` clausola [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per ignorare le prime quattro stringhe in una matrice di stringhe prima di restituire le stringhe rimanenti della matrice.</span><span class="sxs-lookup"><span data-stu-id="01e8e-133">The following code example uses the `Skip` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 <span data-ttu-id="01e8e-134">[!code-vb[CsLINQPartitioning n.&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="01e8e-134">[!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span></span>  
  
### <a name="skipwhile"></a><span data-ttu-id="01e8e-135">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="01e8e-135">SkipWhile</span></span>  
 <span data-ttu-id="01e8e-136">Nell'esempio di codice viene illustrato come utilizzare il `Skip While` clausola [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per ignorare le stringhe in una matrice durante la prima lettera della stringa è "a".</span><span class="sxs-lookup"><span data-stu-id="01e8e-136">The following code example uses the `Skip While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="01e8e-137">Le stringhe rimanenti della matrice vengono restituite.</span><span class="sxs-lookup"><span data-stu-id="01e8e-137">The remaining strings in the array are returned.</span></span>  
  
 <span data-ttu-id="01e8e-138">[!code-vb[CsLINQPartitioning n.&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="01e8e-138">[!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span></span>  
  
### <a name="take"></a><span data-ttu-id="01e8e-139">Take</span><span class="sxs-lookup"><span data-stu-id="01e8e-139">Take</span></span>  
 <span data-ttu-id="01e8e-140">Nell'esempio di codice viene illustrato come utilizzare il `Take` clausola [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per restituire le prime due stringhe in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="01e8e-140">The following code example uses the `Take` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return the first two strings in an array of strings.</span></span>  
  
 <span data-ttu-id="01e8e-141">[!code-vb[CsLINQPartitioning n.&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="01e8e-141">[!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span></span>  
  
### <a name="takewhile"></a><span data-ttu-id="01e8e-142">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="01e8e-142">TakeWhile</span></span>  
 <span data-ttu-id="01e8e-143">Nell'esempio di codice viene illustrato come utilizzare il `Take While` clausola [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per restituire le stringhe da una matrice, mentre la lunghezza della stringa è di cinque o meno.</span><span class="sxs-lookup"><span data-stu-id="01e8e-143">The following code example uses the `Take While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return strings from an array while the length of the string is five or less.</span></span>  
  
 <span data-ttu-id="01e8e-144">[!code-vb[CsLINQPartitioning n.&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="01e8e-144">[!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e8e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e8e-145">See Also</span></span>  
 <span data-ttu-id="01e8e-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="01e8e-146"><xref:System.Linq></span></span>   
<span data-ttu-id="01e8e-147"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="01e8e-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="01e8e-148"> [Clausola Skip](../../../../visual-basic/language-reference/queries/skip-clause.md) </span><span class="sxs-lookup"><span data-stu-id="01e8e-148"> [Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md) </span></span>  
<span data-ttu-id="01e8e-149"> [Clausola Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span><span class="sxs-lookup"><span data-stu-id="01e8e-149"> [Skip While Clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span></span>  
<span data-ttu-id="01e8e-150"> [Clausola Take](../../../../visual-basic/language-reference/queries/take-clause.md) </span><span class="sxs-lookup"><span data-stu-id="01e8e-150"> [Take Clause](../../../../visual-basic/language-reference/queries/take-clause.md) </span></span>  
<span data-ttu-id="01e8e-151"> [Clausola Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span><span class="sxs-lookup"><span data-stu-id="01e8e-151"> [Take While Clause](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span></span>
