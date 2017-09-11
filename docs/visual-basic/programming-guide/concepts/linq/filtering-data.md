---
title: Filtraggio dei dati (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fa2d3b6c5b81f137ab3a81f9b18707bb2da91f6e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="39806-102">Il filtraggio dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39806-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="39806-103">Il filtro fa riferimento all'operazione di limitare il set di risultati a contenere solo gli elementi che soddisfano una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="39806-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="39806-104">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="39806-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="39806-105">Nella figura seguente mostra i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="39806-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="39806-106">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="39806-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="39806-107">![Operazione di filtraggio LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="39806-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="39806-108">Nella sezione seguente sono elencati i metodi dell'operatore query standard che eseguono la selezione.</span><span class="sxs-lookup"><span data-stu-id="39806-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39806-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="39806-109">Methods</span></span>  
  
|<span data-ttu-id="39806-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="39806-110">Method Name</span></span>|<span data-ttu-id="39806-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39806-111">Description</span></span>|<span data-ttu-id="39806-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39806-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="39806-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="39806-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="39806-114">OfType</span><span class="sxs-lookup"><span data-stu-id="39806-114">OfType</span></span>|<span data-ttu-id="39806-115">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="39806-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="39806-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="39806-116">Not applicable.</span></span>|<span data-ttu-id="39806-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="39806-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="39806-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="39806-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="39806-119">Dove</span><span class="sxs-lookup"><span data-stu-id="39806-119">Where</span></span>|<span data-ttu-id="39806-120">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="39806-120">Selects values that are based on a predicate function.</span></span>|`Where`|<span data-ttu-id="39806-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="39806-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="39806-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="39806-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="39806-123">Esempio di sintassi di espressione di query</span><span class="sxs-lookup"><span data-stu-id="39806-123">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="39806-124">Nell'esempio seguente viene utilizzata la `Where` per filtrare da una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="39806-124">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="39806-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39806-125">See Also</span></span>  
 <span data-ttu-id="39806-126"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="39806-126"><xref:System.Linq></span></span>   
<span data-ttu-id="39806-127"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="39806-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="39806-128"> [In cui clausola](../../../../visual-basic/language-reference/queries/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="39806-128"> [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) </span></span>  
<span data-ttu-id="39806-129"> [Procedura: filtrare i risultati della Query](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="39806-129"> [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="39806-130"> [Procedura: eseguire Query sui metadati di un Assembly tramite Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="39806-130"> [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
<span data-ttu-id="39806-131"> [Procedura: eseguire una Query per i file con un attributo specificato o un nome (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="39806-131"> [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
<span data-ttu-id="39806-132"> [Procedura: ordinare o filtrare i dati di testo da qualsiasi parola o campo (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="39806-132"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
