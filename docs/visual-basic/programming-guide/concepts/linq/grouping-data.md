---
title: Raggruppamento dei dati (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: c658ac5c46baec1bfa976074b78ac86d791b6515
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842057"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="292c4-102">Raggruppamento dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="292c4-103">Il raggruppamento consiste nell'inserire i dati in gruppi in modo che gli elementi in ogni gruppo condividano un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="292c4-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="292c4-104">Nella figura seguente vengono illustrati i risultati del raggruppamento di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="292c4-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="292c4-105">La chiave di ogni gruppo è il carattere.</span><span class="sxs-lookup"><span data-stu-id="292c4-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="292c4-106">![Operazioni di raggruppamento LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="292c4-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="292c4-107">Nella sezione seguente vengono elencati i metodi degli operatori query standard che eseguono il raggruppamento degli elementi di dati.</span><span class="sxs-lookup"><span data-stu-id="292c4-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="292c4-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="292c4-108">Methods</span></span>  
  
|<span data-ttu-id="292c4-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="292c4-109">Method Name</span></span>|<span data-ttu-id="292c4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="292c4-110">Description</span></span>|<span data-ttu-id="292c4-111">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="292c4-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="292c4-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="292c4-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="292c4-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="292c4-113">GroupBy</span></span>|<span data-ttu-id="292c4-114">Raggruppa gli elementi che condividono un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="292c4-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="292c4-115">Ogni gruppo è rappresentato da un oggetto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="292c4-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="292c4-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="292c4-116">ToLookup</span></span>|<span data-ttu-id="292c4-117">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="292c4-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="292c4-118">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="292c4-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="292c4-119">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="292c4-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="292c4-120">Nell'esempio di codice seguente viene illustrato come usare la clausola `Group By` per raggruppare i numeri interi in un elenco a seconda che siano numeri pari o numeri dispari.</span><span class="sxs-lookup"><span data-stu-id="292c4-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="292c4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="292c4-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="292c4-122">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="292c4-123">Clausola Group By</span><span class="sxs-lookup"><span data-stu-id="292c4-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="292c4-124">Procedura: Raggruppa file per estensione (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="292c4-125">Procedura: Suddividere un File in molti file usando i gruppi (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
