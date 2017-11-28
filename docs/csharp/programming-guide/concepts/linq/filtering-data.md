---
title: Filtro di dati (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77a68d5fa0fa606a7d164adf187c8aa0027170bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="filtering-data-c"></a><span data-ttu-id="ec638-102">Filtro di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="ec638-102">Filtering Data (C#)</span></span>
<span data-ttu-id="ec638-103">Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="ec638-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="ec638-104">È anche noto come selezione.</span><span class="sxs-lookup"><span data-stu-id="ec638-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="ec638-105">Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="ec638-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="ec638-106">Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.</span><span class="sxs-lookup"><span data-stu-id="ec638-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="ec638-107">![Operazione di filtro LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="ec638-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="ec638-108">La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.</span><span class="sxs-lookup"><span data-stu-id="ec638-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec638-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="ec638-109">Methods</span></span>  
  
|<span data-ttu-id="ec638-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="ec638-110">Method Name</span></span>|<span data-ttu-id="ec638-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec638-111">Description</span></span>|<span data-ttu-id="ec638-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="ec638-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="ec638-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ec638-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ec638-114">OfType</span><span class="sxs-lookup"><span data-stu-id="ec638-114">OfType</span></span>|<span data-ttu-id="ec638-115">Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ec638-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="ec638-116">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="ec638-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ec638-117">Dove</span><span class="sxs-lookup"><span data-stu-id="ec638-117">Where</span></span>|<span data-ttu-id="ec638-118">Seleziona i valori che si basano su una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="ec638-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="ec638-119">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ec638-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="ec638-120">Nell'esempio seguente viene usata la clausola `where` per filtrare da una matrice le stringhe con una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="ec638-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec638-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec638-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="ec638-122">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="ec638-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="ec638-123">Clausola where</span><span class="sxs-lookup"><span data-stu-id="ec638-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)  
 [<span data-ttu-id="ec638-124">Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ec638-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
 [<span data-ttu-id="ec638-125">Procedura: Eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ec638-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="ec638-126">Procedura: Eseguire una query per trovare i file con un attributo o un nome specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="ec638-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="ec638-127">Procedura: Ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ec638-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
