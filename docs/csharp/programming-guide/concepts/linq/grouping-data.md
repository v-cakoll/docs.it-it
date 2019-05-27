---
title: Raggruppamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: a85babc43f673711fe1bdfa5cec1836a5073c785
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753923"
---
# <a name="grouping-data-c"></a><span data-ttu-id="29796-102">Raggruppamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="29796-102">Grouping Data (C#)</span></span>
<span data-ttu-id="29796-103">Il raggruppamento consiste nell'inserire i dati in gruppi in modo che gli elementi in ogni gruppo condividano un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="29796-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="29796-104">Nella figura seguente vengono illustrati i risultati del raggruppamento di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="29796-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="29796-105">La chiave di ogni gruppo è il carattere.</span><span class="sxs-lookup"><span data-stu-id="29796-105">The key for each group is the character.</span></span>  
  
 ![Diagramma che illustra un'operazione di raggruppamento LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="29796-107">Nella sezione seguente vengono elencati i metodi degli operatori query standard che eseguono il raggruppamento degli elementi di dati.</span><span class="sxs-lookup"><span data-stu-id="29796-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29796-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="29796-108">Methods</span></span>  
  
|<span data-ttu-id="29796-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="29796-109">Method Name</span></span>|<span data-ttu-id="29796-110">Description</span><span class="sxs-lookup"><span data-stu-id="29796-110">Description</span></span>|<span data-ttu-id="29796-111">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="29796-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="29796-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="29796-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="29796-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="29796-113">GroupBy</span></span>|<span data-ttu-id="29796-114">Raggruppa gli elementi che condividono un attributo comune.</span><span class="sxs-lookup"><span data-stu-id="29796-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="29796-115">Ogni gruppo è rappresentato da un oggetto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="29796-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="29796-116">-oppure-</span><span class="sxs-lookup"><span data-stu-id="29796-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="29796-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="29796-117">ToLookup</span></span>|<span data-ttu-id="29796-118">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="29796-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="29796-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="29796-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="29796-120">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="29796-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="29796-121">Nell'esempio di codice seguente viene illustrato come usare la clausola `group by` per raggruppare i numeri interi in un elenco a seconda che siano numeri pari o numeri dispari.</span><span class="sxs-lookup"><span data-stu-id="29796-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29796-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29796-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="29796-123">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="29796-123">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="29796-124">Clausola group</span><span class="sxs-lookup"><span data-stu-id="29796-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)
- [<span data-ttu-id="29796-125">Procedura: Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="29796-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)
- [<span data-ttu-id="29796-126">Procedura: Raggruppare file per estensione (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="29796-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="29796-127">Procedura: Raggruppare i risultati di una query</span><span class="sxs-lookup"><span data-stu-id="29796-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)
- [<span data-ttu-id="29796-128">Procedura: Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="29796-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="29796-129">Procedura: Suddividere un file in molti file usando i gruppi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="29796-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
