---
title: Raggruppamento dei dati (C#)
description: Il raggruppamento inserisce i dati in gruppi di elementi che condividono un attributo. Informazioni sui metodi dell'operatore query standard in LINQ in C# che raggruppano gli elementi dati.
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 5e1bca1d360b0f44a081cf2770118a0551629b5b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103681"
---
# <a name="grouping-data-c"></a><span data-ttu-id="a80c8-104">Raggruppamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="a80c8-104">Grouping Data (C#)</span></span>
<span data-ttu-id="a80c8-105">Il raggruppamento consiste nell'inserire i dati in gruppi in modo che gli elementi in ogni gruppo condividano un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="a80c8-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="a80c8-106">Nella figura seguente vengono illustrati i risultati del raggruppamento di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="a80c8-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="a80c8-107">La chiave di ogni gruppo è il carattere.</span><span class="sxs-lookup"><span data-stu-id="a80c8-107">The key for each group is the character.</span></span>  
  
 ![Diagramma che illustra un'operazione di raggruppamento LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="a80c8-109">Nella sezione seguente vengono elencati i metodi degli operatori query standard che eseguono il raggruppamento degli elementi di dati.</span><span class="sxs-lookup"><span data-stu-id="a80c8-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a80c8-110">Metodi</span><span class="sxs-lookup"><span data-stu-id="a80c8-110">Methods</span></span>  
  
|<span data-ttu-id="a80c8-111">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="a80c8-111">Method Name</span></span>|<span data-ttu-id="a80c8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a80c8-112">Description</span></span>|<span data-ttu-id="a80c8-113">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="a80c8-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="a80c8-114">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a80c8-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="a80c8-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="a80c8-115">GroupBy</span></span>|<span data-ttu-id="a80c8-116">Raggruppa gli elementi che condividono un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="a80c8-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="a80c8-117">Ogni gruppo è rappresentato da un oggetto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="a80c8-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="a80c8-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a80c8-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a80c8-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="a80c8-119">ToLookup</span></span>|<span data-ttu-id="a80c8-120">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="a80c8-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="a80c8-121">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a80c8-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="a80c8-122">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="a80c8-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="a80c8-123">Nell'esempio di codice seguente viene illustrato come usare la clausola `group by` per raggruppare i numeri interi in un elenco a seconda che siano numeri pari o numeri dispari.</span><span class="sxs-lookup"><span data-stu-id="a80c8-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="a80c8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a80c8-124">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="a80c8-125">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="a80c8-125">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="a80c8-126">Clausola group</span><span class="sxs-lookup"><span data-stu-id="a80c8-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="a80c8-127">Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="a80c8-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="a80c8-128">Come raggruppare i file per estensione (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a80c8-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="a80c8-129">Raggruppare i risultati di una query</span><span class="sxs-lookup"><span data-stu-id="a80c8-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="a80c8-130">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="a80c8-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="a80c8-131">Come suddividere un file in molti file usando i gruppi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a80c8-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
