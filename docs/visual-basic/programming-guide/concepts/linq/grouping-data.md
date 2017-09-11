---
title: Raggruppamento di dati (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
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
ms.openlocfilehash: ce4e8f924f91eed451d3b1a02cd0bcff75589537
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="750d6-102">Raggruppamento di dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="750d6-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="750d6-103">Raggruppamento si riferisce all'operazione di inserimento dati in gruppi in modo che gli elementi in ciascun gruppo condividano un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="750d6-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="750d6-104">Nella figura seguente mostra i risultati di una sequenza di caratteri di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="750d6-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="750d6-105">La chiave per ogni gruppo è il carattere.</span><span class="sxs-lookup"><span data-stu-id="750d6-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="750d6-106">![Operazioni di raggruppamento LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="750d6-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="750d6-107">Nella sezione seguente sono elencati i metodi degli operatori di query standard che raggruppare gli elementi di dati.</span><span class="sxs-lookup"><span data-stu-id="750d6-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="750d6-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="750d6-108">Methods</span></span>  
  
|<span data-ttu-id="750d6-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="750d6-109">Method Name</span></span>|<span data-ttu-id="750d6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="750d6-110">Description</span></span>|<span data-ttu-id="750d6-111">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="750d6-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="750d6-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="750d6-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="750d6-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="750d6-113">GroupBy</span></span>|<span data-ttu-id="750d6-114">Raggruppa gli elementi che condividono un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="750d6-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="750d6-115">Ogni gruppo è rappresentato da un <xref:System.Linq.IGrouping%602>oggetto.</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="750d6-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<span data-ttu-id="750d6-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="750d6-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="750d6-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="750d6-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="750d6-118">ToLookup</span><span class="sxs-lookup"><span data-stu-id="750d6-118">ToLookup</span></span>|<span data-ttu-id="750d6-119">Inserisce gli elementi in un <xref:System.Linq.Lookup%602>(un dizionario uno-a-molti) in base a una funzione selettore di chiave.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="750d6-119">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="750d6-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="750d6-120">Not applicable.</span></span>|<span data-ttu-id="750d6-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="750d6-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="750d6-122">Esempio di sintassi di espressione di query</span><span class="sxs-lookup"><span data-stu-id="750d6-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="750d6-123">Nell'esempio di codice viene illustrato come utilizzare il `Group By` clausola per raggruppare i numeri interi in un elenco in base al fatto che siano pari o dispari.</span><span class="sxs-lookup"><span data-stu-id="750d6-123">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="750d6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="750d6-124">See Also</span></span>  
 <span data-ttu-id="750d6-125"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="750d6-125"><xref:System.Linq></span></span>   
<span data-ttu-id="750d6-126"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="750d6-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="750d6-127"> [Clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="750d6-127"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span></span>  
<span data-ttu-id="750d6-128"> [Procedura: raggruppare i file per estensione (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="750d6-128"> [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
<span data-ttu-id="750d6-129"> [Procedura: suddividere un File in molti file utilizzando i gruppi (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="750d6-129"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
