---
title: Conversione di tipi di dati (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 9e8b7726b94871a17a4be50a9b24d8b73abcf79c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594611"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="1fe4e-102">Conversione di tipi di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="1fe4e-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="1fe4e-103">I metodi di conversione modificano il tipo degli oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="1fe4e-104">Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="1fe4e-105">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="1fe4e-105">Following are some examples:</span></span>  
  
- <span data-ttu-id="1fe4e-106">Il metodo <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> può essere usato per nascondere l'implementazione personalizzata di un tipo di un operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
- <span data-ttu-id="1fe4e-107">Il metodo <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> può essere usato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
- <span data-ttu-id="1fe4e-108">I metodi <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> possono essere usati per forzare l'esecuzione di una query immediata invece che rinviarla fino a quando la query non viene enumerata.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fe4e-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="1fe4e-109">Methods</span></span>  
 <span data-ttu-id="1fe4e-110">Nella tabella seguente sono elencati i metodi di operatore query standard che eseguono conversioni di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="1fe4e-111">I metodi di conversione nella tabella i cui nomi iniziano con "As" modificano il tipo statico della raccolta di origine ma non lo enumerano.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="1fe4e-112">I metodi i cui nomi iniziano con "To" enumerano la raccolta di origine e inseriscono gli elementi nel tipo di raccolta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="1fe4e-113">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="1fe4e-113">Method Name</span></span>|<span data-ttu-id="1fe4e-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1fe4e-114">Description</span></span>|<span data-ttu-id="1fe4e-115">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="1fe4e-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="1fe4e-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="1fe4e-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="1fe4e-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="1fe4e-117">AsEnumerable</span></span>|<span data-ttu-id="1fe4e-118">Restituisce l'input tipizzato come oggetto <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="1fe4e-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="1fe4e-120">AsQueryable</span></span>|<span data-ttu-id="1fe4e-121">Converte un oggetto <xref:System.Collections.IEnumerable> (generico) in un oggetto <xref:System.Linq.IQueryable> (generico).</span><span class="sxs-lookup"><span data-stu-id="1fe4e-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="1fe4e-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-123">Cast</span><span class="sxs-lookup"><span data-stu-id="1fe4e-123">Cast</span></span>|<span data-ttu-id="1fe4e-124">Esegue il cast degli elementi di una raccolta a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="1fe4e-125">Usare una variabile di intervallo tipizzata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="1fe4e-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1fe4e-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-127">OfType</span><span class="sxs-lookup"><span data-stu-id="1fe4e-127">OfType</span></span>|<span data-ttu-id="1fe4e-128">Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="1fe4e-129">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="1fe4e-130">ToArray</span></span>|<span data-ttu-id="1fe4e-131">Converte una raccolta in una matrice.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-131">Converts a collection to an array.</span></span> <span data-ttu-id="1fe4e-132">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-132">This method forces query execution.</span></span>|<span data-ttu-id="1fe4e-133">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="1fe4e-134">ToDictionary</span></span>|<span data-ttu-id="1fe4e-135">Inserisce gli elementi in un oggetto <xref:System.Collections.Generic.Dictionary%602> sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="1fe4e-136">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-136">This method forces query execution.</span></span>|<span data-ttu-id="1fe4e-137">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-138">ToList</span><span class="sxs-lookup"><span data-stu-id="1fe4e-138">ToList</span></span>|<span data-ttu-id="1fe4e-139">Converte una raccolta in un oggetto <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="1fe4e-140">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-140">This method forces query execution.</span></span>|<span data-ttu-id="1fe4e-141">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fe4e-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="1fe4e-142">ToLookup</span></span>|<span data-ttu-id="1fe4e-143">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="1fe4e-144">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-144">This method forces query execution.</span></span>|<span data-ttu-id="1fe4e-145">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="1fe4e-146">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="1fe4e-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="1fe4e-147">L'esempio di codice seguente usa una variabile di intervallo tipizzata in modo esplicito per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro che è disponibile solo nel sottotipo.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fe4e-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fe4e-148">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="1fe4e-149">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="1fe4e-149">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="1fe4e-150">Clausola from</span><span class="sxs-lookup"><span data-stu-id="1fe4e-150">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="1fe4e-151">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="1fe4e-151">LINQ Query Expressions</span></span>](../../linq-query-expressions/index.md)
- [<span data-ttu-id="1fe4e-152">Procedura: Eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="1fe4e-152">How to: Query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
