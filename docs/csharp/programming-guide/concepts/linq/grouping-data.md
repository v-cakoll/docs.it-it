---
title: Raggruppamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 7ef3d3c9097d7a9478605565518ac8975feb9fe2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635743"
---
# <a name="grouping-data-c"></a><span data-ttu-id="b2d67-102">Raggruppamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="b2d67-102">Grouping Data (C#)</span></span>
<span data-ttu-id="b2d67-103">Il raggruppamento consiste nell'inserire i dati in gruppi in modo che gli elementi in ogni gruppo condividano un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="b2d67-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="b2d67-104">Nella figura seguente vengono illustrati i risultati del raggruppamento di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="b2d67-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="b2d67-105">La chiave di ogni gruppo è il carattere.</span><span class="sxs-lookup"><span data-stu-id="b2d67-105">The key for each group is the character.</span></span>  
  
 ![Diagramma che illustra un'operazione di raggruppamento LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="b2d67-107">Nella sezione seguente vengono elencati i metodi degli operatori query standard che eseguono il raggruppamento degli elementi di dati.</span><span class="sxs-lookup"><span data-stu-id="b2d67-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2d67-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="b2d67-108">Methods</span></span>  
  
|<span data-ttu-id="b2d67-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="b2d67-109">Method Name</span></span>|<span data-ttu-id="b2d67-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2d67-110">Description</span></span>|<span data-ttu-id="b2d67-111">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="b2d67-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="b2d67-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b2d67-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b2d67-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="b2d67-113">GroupBy</span></span>|<span data-ttu-id="b2d67-114">Raggruppa gli elementi che condividono un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="b2d67-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="b2d67-115">Ogni gruppo è rappresentato da un oggetto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="b2d67-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="b2d67-116">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b2d67-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b2d67-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="b2d67-117">ToLookup</span></span>|<span data-ttu-id="b2d67-118">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b2d67-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="b2d67-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="b2d67-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="b2d67-120">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b2d67-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="b2d67-121">Nell'esempio di codice seguente viene illustrato come usare la clausola `group by` per raggruppare i numeri interi in un elenco a seconda che siano numeri pari o numeri dispari.</span><span class="sxs-lookup"><span data-stu-id="b2d67-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2d67-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2d67-122">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="b2d67-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="b2d67-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="b2d67-124">Clausola group</span><span class="sxs-lookup"><span data-stu-id="b2d67-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="b2d67-125">Creare un gruppo nidificato</span><span class="sxs-lookup"><span data-stu-id="b2d67-125">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="b2d67-126">Come raggruppare i file in base all'estensione (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="b2d67-126">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="b2d67-127">Raggruppare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="b2d67-127">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="b2d67-128">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="b2d67-128">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="b2d67-129">Come dividere un file in molti file utilizzando i gruppi (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="b2d67-129">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
