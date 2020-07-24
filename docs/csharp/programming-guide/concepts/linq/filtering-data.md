---
title: Filtro di dati (C#)
description: Il filtro, noto anche come selezione, limita i risultati in base a una condizione. Informazioni sui metodi dell'operatore query standard in LINQ in C# che eseguono il filtro.
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: f9f6d691da73b566e5135f6692c87ba3a8978005
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103926"
---
# <a name="filtering-data-c"></a><span data-ttu-id="ee30a-104">Filtro di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="ee30a-104">Filtering Data (C#)</span></span>
<span data-ttu-id="ee30a-105">Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="ee30a-105">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="ee30a-106">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="ee30a-106">It is also known as selection.</span></span>  
  
 <span data-ttu-id="ee30a-107">Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="ee30a-107">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="ee30a-108">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="ee30a-108">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Diagramma che illustra un'operazione di filtro LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="ee30a-110">La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.</span><span class="sxs-lookup"><span data-stu-id="ee30a-110">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee30a-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="ee30a-111">Methods</span></span>  
  
|<span data-ttu-id="ee30a-112">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="ee30a-112">Method Name</span></span>|<span data-ttu-id="ee30a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee30a-113">Description</span></span>|<span data-ttu-id="ee30a-114">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="ee30a-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="ee30a-115">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ee30a-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ee30a-116">OfType</span><span class="sxs-lookup"><span data-stu-id="ee30a-116">OfType</span></span>|<span data-ttu-id="ee30a-117">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ee30a-117">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="ee30a-118">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="ee30a-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ee30a-119">Where</span><span class="sxs-lookup"><span data-stu-id="ee30a-119">Where</span></span>|<span data-ttu-id="ee30a-120">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="ee30a-120">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="ee30a-121">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ee30a-121">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="ee30a-122">Nell'esempio seguente viene usata la clausola `where` per filtrare da una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="ee30a-122">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee30a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee30a-123">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="ee30a-124">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="ee30a-124">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="ee30a-125">clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="ee30a-125">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="ee30a-126">Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ee30a-126">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="ee30a-127">Come eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ee30a-127">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="ee30a-128">Come eseguire una query per i file con un attributo o un nome specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="ee30a-128">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="ee30a-129">Come ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ee30a-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
