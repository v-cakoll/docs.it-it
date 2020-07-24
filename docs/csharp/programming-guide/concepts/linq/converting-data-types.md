---
title: Conversione di tipi di dati (C#)
description: I metodi di conversione modificano il tipo degli oggetti di input. Vedere operazioni di conversione nelle query LINQ in C#, ad esempio Enumerable. AsEnumerable ed Enumerable. OfType.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 3291690f9aaee945ca7feb04ebbc676db2612894
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105489"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="bd0d4-104">Conversione di tipi di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="bd0d4-104">Converting Data Types (C#)</span></span>
<span data-ttu-id="bd0d4-105">I metodi di conversione modificano il tipo degli oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-105">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="bd0d4-106">Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-106">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="bd0d4-107">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="bd0d4-107">Following are some examples:</span></span>

- <span data-ttu-id="bd0d4-108">Il metodo <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> può essere usato per nascondere l'implementazione personalizzata di un tipo di un operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-108">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="bd0d4-109">Il metodo <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> può essere usato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-109">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="bd0d4-110">I metodi <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> possono essere usati per forzare l'esecuzione di una query immediata invece che rinviarla fino a quando la query non viene enumerata.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-110">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="bd0d4-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="bd0d4-111">Methods</span></span>
 <span data-ttu-id="bd0d4-112">Nella tabella seguente sono elencati i metodi di operatore query standard che eseguono conversioni di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-112">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="bd0d4-113">I metodi di conversione nella tabella i cui nomi iniziano con "As" modificano il tipo statico della raccolta di origine ma non lo enumerano.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-113">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="bd0d4-114">I metodi i cui nomi iniziano con "To" enumerano la raccolta di origine e inseriscono gli elementi nel tipo di raccolta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-114">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="bd0d4-115">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="bd0d4-115">Method Name</span></span>|<span data-ttu-id="bd0d4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd0d4-116">Description</span></span>|<span data-ttu-id="bd0d4-117">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="bd0d4-117">C# Query Expression Syntax</span></span>|<span data-ttu-id="bd0d4-118">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="bd0d4-118">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="bd0d4-119">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="bd0d4-119">AsEnumerable</span></span>|<span data-ttu-id="bd0d4-120">Restituisce l'input tipizzato come oggetto <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-120">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="bd0d4-121">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-122">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="bd0d4-122">AsQueryable</span></span>|<span data-ttu-id="bd0d4-123">Converte un oggetto <xref:System.Collections.IEnumerable> (generico) in un oggetto <xref:System.Linq.IQueryable> (generico).</span><span class="sxs-lookup"><span data-stu-id="bd0d4-123">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="bd0d4-124">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-124">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-125">Cast</span><span class="sxs-lookup"><span data-stu-id="bd0d4-125">Cast</span></span>|<span data-ttu-id="bd0d4-126">Esegue il cast degli elementi di una raccolta a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-126">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="bd0d4-127">Usare una variabile di intervallo tipizzata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-127">Use an explicitly typed range variable.</span></span> <span data-ttu-id="bd0d4-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bd0d4-128">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-129">OfType</span><span class="sxs-lookup"><span data-stu-id="bd0d4-129">OfType</span></span>|<span data-ttu-id="bd0d4-130">Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="bd0d4-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-132">ToArray</span><span class="sxs-lookup"><span data-stu-id="bd0d4-132">ToArray</span></span>|<span data-ttu-id="bd0d4-133">Converte una raccolta in una matrice.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-133">Converts a collection to an array.</span></span> <span data-ttu-id="bd0d4-134">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-134">This method forces query execution.</span></span>|<span data-ttu-id="bd0d4-135">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-136">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="bd0d4-136">ToDictionary</span></span>|<span data-ttu-id="bd0d4-137">Inserisce gli elementi in un oggetto <xref:System.Collections.Generic.Dictionary%602> sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-137">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="bd0d4-138">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-138">This method forces query execution.</span></span>|<span data-ttu-id="bd0d4-139">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-140">ToList</span><span class="sxs-lookup"><span data-stu-id="bd0d4-140">ToList</span></span>|<span data-ttu-id="bd0d4-141">Converte una raccolta in un oggetto <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-141">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="bd0d4-142">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-142">This method forces query execution.</span></span>|<span data-ttu-id="bd0d4-143">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="bd0d4-144">ToLookup</span><span class="sxs-lookup"><span data-stu-id="bd0d4-144">ToLookup</span></span>|<span data-ttu-id="bd0d4-145">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-145">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="bd0d4-146">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-146">This method forces query execution.</span></span>|<span data-ttu-id="bd0d4-147">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-147">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="bd0d4-148">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="bd0d4-148">Query Expression Syntax Example</span></span>

<span data-ttu-id="bd0d4-149">Nell'esempio di codice seguente viene utilizzata una variabile di intervallo tipizzata in modo esplicito per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro disponibile solo sul sottotipo.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-149">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a><span data-ttu-id="bd0d4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd0d4-150">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="bd0d4-151">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="bd0d4-151">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="bd0d4-152">clausola from</span><span class="sxs-lookup"><span data-stu-id="bd0d4-152">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="bd0d4-153">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="bd0d4-153">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="bd0d4-154">Come eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="bd0d4-154">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
