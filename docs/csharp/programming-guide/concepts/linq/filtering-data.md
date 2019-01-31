---
title: Filtro di dati (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: dc31a73a8ebbe52f7d22984cd747a038e2556c28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634636"
---
# <a name="filtering-data-c"></a><span data-ttu-id="6c8d9-102">Filtro di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="6c8d9-102">Filtering Data (C#)</span></span>
<span data-ttu-id="6c8d9-103">Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="6c8d9-104">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="6c8d9-105">Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="6c8d9-106">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="6c8d9-107">![Operazione di filtro LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="6c8d9-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="6c8d9-108">La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c8d9-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="6c8d9-109">Methods</span></span>  
  
|<span data-ttu-id="6c8d9-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="6c8d9-110">Method Name</span></span>|<span data-ttu-id="6c8d9-111">Description</span><span class="sxs-lookup"><span data-stu-id="6c8d9-111">Description</span></span>|<span data-ttu-id="6c8d9-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="6c8d9-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="6c8d9-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6c8d9-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="6c8d9-114">OfType</span><span class="sxs-lookup"><span data-stu-id="6c8d9-114">OfType</span></span>|<span data-ttu-id="6c8d9-115">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="6c8d9-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6c8d9-117">Dove</span><span class="sxs-lookup"><span data-stu-id="6c8d9-117">Where</span></span>|<span data-ttu-id="6c8d9-118">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="6c8d9-119">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="6c8d9-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="6c8d9-120">Nell'esempio seguente viene usata la clausola `where` per filtrare da una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="6c8d9-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c8d9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c8d9-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="6c8d9-122">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="6c8d9-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6c8d9-123">Clausola where</span><span class="sxs-lookup"><span data-stu-id="6c8d9-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)
- [<span data-ttu-id="6c8d9-124">Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6c8d9-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="6c8d9-125">Procedura: Eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c8d9-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="6c8d9-126">Procedura: Eseguire una query per trovare i file con un attributo o un nome specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="6c8d9-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="6c8d9-127">Procedura: Ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c8d9-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
