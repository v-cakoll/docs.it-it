---
title: Conversione di tipi di dati (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 454fb0ce937d7d20dfce26d92dbf49de24f062f0
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="converting-data-types-c"></a><span data-ttu-id="4b631-102">Conversione di tipi di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="4b631-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="4b631-103">I metodi di conversione modificano il tipo degli oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="4b631-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="4b631-104">Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4b631-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="4b631-105">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="4b631-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="4b631-106">Il metodo <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> può essere usato per nascondere l'implementazione personalizzata di un tipo di un operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="4b631-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="4b631-107">Il metodo <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> può essere usato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="4b631-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="4b631-108">I metodi <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> possono essere usati per forzare l'esecuzione di una query immediata invece che rinviarla fino a quando la query non viene enumerata.</span><span class="sxs-lookup"><span data-stu-id="4b631-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b631-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="4b631-109">Methods</span></span>  
 <span data-ttu-id="4b631-110">Nella tabella seguente sono elencati i metodi di operatore query standard che eseguono conversioni di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="4b631-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="4b631-111">I metodi di conversione nella tabella i cui nomi iniziano con "As" modificano il tipo statico della raccolta di origine ma non lo enumerano.</span><span class="sxs-lookup"><span data-stu-id="4b631-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="4b631-112">I metodi i cui nomi iniziano con "To" enumerano la raccolta di origine e inseriscono gli elementi nel tipo di raccolta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4b631-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="4b631-113">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="4b631-113">Method Name</span></span>|<span data-ttu-id="4b631-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b631-114">Description</span></span>|<span data-ttu-id="4b631-115">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="4b631-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="4b631-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="4b631-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="4b631-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="4b631-117">AsEnumerable</span></span>|<span data-ttu-id="4b631-118">Restituisce l'input tipizzato come oggetto <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="4b631-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="4b631-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="4b631-120">AsQueryable</span></span>|<span data-ttu-id="4b631-121">Converte un oggetto <xref:System.Collections.IEnumerable> (generico) in un oggetto <xref:System.Linq.IQueryable> (generico).</span><span class="sxs-lookup"><span data-stu-id="4b631-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="4b631-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-123">Cast</span><span class="sxs-lookup"><span data-stu-id="4b631-123">Cast</span></span>|<span data-ttu-id="4b631-124">Esegue il cast degli elementi di una raccolta a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="4b631-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="4b631-125">Usare una variabile di intervallo tipizzata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="4b631-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="4b631-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b631-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-127">OfType</span><span class="sxs-lookup"><span data-stu-id="4b631-127">OfType</span></span>|<span data-ttu-id="4b631-128">Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="4b631-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="4b631-129">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="4b631-130">ToArray</span></span>|<span data-ttu-id="4b631-131">Converte una raccolta in una matrice.</span><span class="sxs-lookup"><span data-stu-id="4b631-131">Converts a collection to an array.</span></span> <span data-ttu-id="4b631-132">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="4b631-132">This method forces query execution.</span></span>|<span data-ttu-id="4b631-133">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="4b631-134">ToDictionary</span></span>|<span data-ttu-id="4b631-135">Inserisce gli elementi in un oggetto <xref:System.Collections.Generic.Dictionary%602> sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="4b631-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="4b631-136">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="4b631-136">This method forces query execution.</span></span>|<span data-ttu-id="4b631-137">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-138">ToList</span><span class="sxs-lookup"><span data-stu-id="4b631-138">ToList</span></span>|<span data-ttu-id="4b631-139">Converte una raccolta in un oggetto <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="4b631-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="4b631-140">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="4b631-140">This method forces query execution.</span></span>|<span data-ttu-id="4b631-141">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|<span data-ttu-id="4b631-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="4b631-142">ToLookup</span></span>|<span data-ttu-id="4b631-143">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="4b631-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="4b631-144">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="4b631-144">This method forces query execution.</span></span>|<span data-ttu-id="4b631-145">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="4b631-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="4b631-146">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="4b631-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="4b631-147">L'esempio di codice seguente usa una variabile di intervallo tipizzata in modo esplicito per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro che è disponibile solo nel sottotipo.</span><span class="sxs-lookup"><span data-stu-id="4b631-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4b631-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b631-148">See Also</span></span>  
 <span data-ttu-id="4b631-149"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="4b631-149"><xref:System.Linq></span></span>   
 <span data-ttu-id="4b631-150">[Cenni preliminari sugli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4b631-150">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="4b631-151">[Clausola From](../../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="4b631-151">[from clause](../../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="4b631-152">[Espressioni di query LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b631-152">[LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="4b631-153">Procedura: Eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="4b631-153">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)

