---
title: Filtraggio dei dati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 31e3a4729a98e1f4b588cd415a15fff270587234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="8f8f9-102">Filtraggio dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f8f9-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="8f8f9-103">Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="8f8f9-104">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="8f8f9-105">Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="8f8f9-106">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="8f8f9-107">![Operazione di filtro LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="8f8f9-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="8f8f9-108">La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f8f9-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="8f8f9-109">Methods</span></span>  
  
|<span data-ttu-id="8f8f9-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="8f8f9-110">Method Name</span></span>|<span data-ttu-id="8f8f9-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8f9-111">Description</span></span>|<span data-ttu-id="8f8f9-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f8f9-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="8f8f9-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="8f8f9-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="8f8f9-114">OfType</span><span class="sxs-lookup"><span data-stu-id="8f8f9-114">OfType</span></span>|<span data-ttu-id="8f8f9-115">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="8f8f9-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8f8f9-117">Dove</span><span class="sxs-lookup"><span data-stu-id="8f8f9-117">Where</span></span>|<span data-ttu-id="8f8f9-118">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="8f8f9-119">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="8f8f9-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="8f8f9-120">L'esempio seguente usa il `Where` per applicare il filtro a una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="8f8f9-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f8f9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f8f9-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="8f8f9-122">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f8f9-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="8f8f9-123">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="8f8f9-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="8f8f9-124">Procedura: Filtrare i risultati di una query</span><span class="sxs-lookup"><span data-stu-id="8f8f9-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)  
 [<span data-ttu-id="8f8f9-125">Procedura: eseguire una Query sui metadati di un Assembly tramite Reflection (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f8f9-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="8f8f9-126">Procedura: eseguire una Query per i file con un attributo specificato o un nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f8f9-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="8f8f9-127">Procedura: ordinare o filtrare i dati di testo da qualsiasi parola o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f8f9-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
