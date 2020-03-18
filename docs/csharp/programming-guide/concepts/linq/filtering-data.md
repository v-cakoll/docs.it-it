---
title: Filtro di dati (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 74399244990f8ff2deaa1d10576ea94a57c16bee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346986"
---
# <a name="filtering-data-c"></a><span data-ttu-id="6028a-102">Filtro di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="6028a-102">Filtering Data (C#)</span></span>
<span data-ttu-id="6028a-103">Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="6028a-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="6028a-104">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="6028a-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="6028a-105">Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="6028a-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="6028a-106">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="6028a-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Diagramma che illustra un'operazione di filtro LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="6028a-108">La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.</span><span class="sxs-lookup"><span data-stu-id="6028a-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6028a-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="6028a-109">Methods</span></span>  
  
|<span data-ttu-id="6028a-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="6028a-110">Method Name</span></span>|<span data-ttu-id="6028a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6028a-111">Description</span></span>|<span data-ttu-id="6028a-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="6028a-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="6028a-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6028a-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="6028a-114">OfType</span><span class="sxs-lookup"><span data-stu-id="6028a-114">OfType</span></span>|<span data-ttu-id="6028a-115">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="6028a-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="6028a-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="6028a-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6028a-117">Where</span><span class="sxs-lookup"><span data-stu-id="6028a-117">Where</span></span>|<span data-ttu-id="6028a-118">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="6028a-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="6028a-119">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="6028a-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="6028a-120">Nell'esempio seguente viene usata la clausola `where` per filtrare da una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="6028a-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6028a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6028a-121">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="6028a-122">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="6028a-122">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="6028a-123">clausola where</span><span class="sxs-lookup"><span data-stu-id="6028a-123">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="6028a-124">Specificare dinamicamente i filtri dei predicati in fase di esecuzioneDynamically specify predicate filters at runtime</span><span class="sxs-lookup"><span data-stu-id="6028a-124">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="6028a-125">Come eseguire una query sui metadati di un assembly con Reflection (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="6028a-125">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="6028a-126">Come eseguire una query per i file con un attributo o un nome specificato (C</span><span class="sxs-lookup"><span data-stu-id="6028a-126">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="6028a-127">Come ordinare o filtrare i dati di testo in base a parole o campi (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="6028a-127">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
