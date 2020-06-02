---
title: Cenni preliminari sugli operatori di query standard (C#)
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 2327ed84734e4f4ad826e02ed4e30b8784a59716
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287419"
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="8c6c8-102">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-102">Standard Query Operators Overview (C#)</span></span>
<span data-ttu-id="8c6c8-103">Gli *operatori di query standard* sono metodi che costituiscono il modello LINQ.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="8c6c8-104">La maggior parte di questi metodi agisce sulle sequenze. Una sequenza è un oggetto il cui tipo implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> o l'interfaccia <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="8c6c8-105">Gli operatori di query standard forniscono le funzionalità di query che includono filtro, proiezione, aggregazione, ordinamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="8c6c8-106">Sono disponibili due set di operatori di query standard LINQ, uno che agisce sugli oggetti di tipo <xref:System.Collections.Generic.IEnumerable%601> e l'altro che agisce sugli oggetti di tipo <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="8c6c8-107">I metodi che costituiscono ogni set sono membri statici delle classi <xref:System.Linq.Enumerable> e <xref:System.Linq.Queryable>, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="8c6c8-108">Vengono definiti come *metodi di estensione* del tipo su cui agiscono.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="8c6c8-109">I metodi di estensione possono essere chiamati usando la sintassi del metodo statico o la sintassi del metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-109">Extension methods can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="8c6c8-110">Inoltre, molti metodi degli operatori query standard agiscono su tipi diversi da quelli basati su <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="8c6c8-111">Il tipo <xref:System.Linq.Enumerable> definisce questi due diversi metodi che agiscono entrambi su oggetti di tipo <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="8c6c8-112">Questi metodi, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> e <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, consentono l'esecuzione di query su una Collection senza parametri o non generica nel modello LINQ</span><span class="sxs-lookup"><span data-stu-id="8c6c8-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="8c6c8-113">A tale scopo, crea una raccolta fortemente tipizzata di oggetti.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-113">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="8c6c8-114">La classe <xref:System.Linq.Queryable> definisce due metodi simili, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> e <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, che agiscono su oggetti di tipo <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="8c6c8-115">Gli operatori di query standard presentano una durata di esecuzione diversa, a seconda che restituiscano un valore singleton o una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="8c6c8-116">Questi metodi che restituiscono un valore singleton, ad esempio <xref:System.Linq.Enumerable.Average%2A> e <xref:System.Linq.Enumerable.Sum%2A>, vengono eseguiti immediatamente.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="8c6c8-117">I metodi che restituiscono una sequenza rinviano l'esecuzione della query e restituiscono un oggetto enumerabile.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="8c6c8-118">Per i metodi che operano su raccolte in memoria, ovvero i metodi che estendono <xref:System.Collections.Generic.IEnumerable%601> , l'oggetto enumerabile restituito acquisisce gli argomenti passati al metodo.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-118">For methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="8c6c8-119">Quando l'oggetto viene enumerato, viene utilizzata la logica dell'operatore query e vengono restituiti i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="8c6c8-120">I metodi che estendono <xref:System.Linq.IQueryable%601> non implementano invece il comportamento delle query, ma compilano un albero delle espressioni che rappresenta la query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="8c6c8-121">L'elaborazione delle query viene gestita dall'oggetto <xref:System.Linq.IQueryable%601> di origine.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="8c6c8-122">Le chiamate ai metodi della query possono essere concatenate in una query, consentendo alle query di diventare arbitrariamente complesse.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="8c6c8-123">Nell'esempio di codice seguente viene illustrato come usare gli operatori di query standard per ottenere informazioni su una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="8c6c8-124">Sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="8c6c8-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="8c6c8-125">Alcuni degli operatori di query standard usati più di frequente dispongono di sintassi dedicata delle parole chiave per i linguaggi C# e Visual Basic che consente di chiamare gli operatori come parte di un'\*espressione di \* *query*.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="8c6c8-126">Per altre informazioni sugli operatori di query standard con parole chiave dedicate e le relative sintassi, vedere [Sintassi di espressione della query per operatori di query standard (C#)](./query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8c6c8-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](./query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="8c6c8-127">Estensione degli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="8c6c8-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="8c6c8-128">È possibile estendere il set di operatori di query standard creando metodi specifici del dominio appropriati per la tecnologia o il dominio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="8c6c8-129">È possibile anche sostituire gli operatori di query standard con implementazioni personalizzate che forniscono servizi aggiuntivi, ad esempio la valutazione remota, la conversione delle query e l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="8c6c8-130">Per un esempio, vedere <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c6c8-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8c6c8-131">Related Sections</span></span>  
 <span data-ttu-id="8c6c8-132">I collegamenti riportati di seguito consentono di passare ad argomenti che forniscono informazioni aggiuntive sui vari operatori di query standard in base alla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8c6c8-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="8c6c8-133">Ordinamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-133">Sorting Data (C#)</span></span>](./sorting-data.md)  
  
 [<span data-ttu-id="8c6c8-134">Operazioni sui set (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-134">Set Operations (C#)</span></span>](./set-operations.md)  
  
 [<span data-ttu-id="8c6c8-135">Filtro di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-135">Filtering Data (C#)</span></span>](./filtering-data.md)  
  
 [<span data-ttu-id="8c6c8-136">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-136">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)  
  
 [<span data-ttu-id="8c6c8-137">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-137">Projection Operations (C#)</span></span>](./projection-operations.md)  
  
 [<span data-ttu-id="8c6c8-138">Partizionamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-138">Partitioning Data (C#)</span></span>](./partitioning-data.md)  
  
 [<span data-ttu-id="8c6c8-139">Operazioni di join (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-139">Join Operations (C#)</span></span>](./join-operations.md)  
  
 [<span data-ttu-id="8c6c8-140">Raggruppamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-140">Grouping Data (C#)</span></span>](./grouping-data.md)  
  
 [<span data-ttu-id="8c6c8-141">Operazioni di generazione (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-141">Generation Operations (C#)</span></span>](./generation-operations.md)  
  
 [<span data-ttu-id="8c6c8-142">Operazioni di uguaglianza (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-142">Equality Operations (C#)</span></span>](./equality-operations.md)  
  
 [<span data-ttu-id="8c6c8-143">Operazioni sugli elementi (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-143">Element Operations (C#)</span></span>](./element-operations.md)  
  
 [<span data-ttu-id="8c6c8-144">Conversione del tipo di dati (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-144">Converting Data Types (C#)</span></span>](./converting-data-types.md)  
  
 [<span data-ttu-id="8c6c8-145">Operazioni di concatenazione (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-145">Concatenation Operations (C#)</span></span>](./concatenation-operations.md)  
  
 [<span data-ttu-id="8c6c8-146">Operazioni di aggregazione (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-146">Aggregation Operations (C#)</span></span>](./aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c6c8-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c6c8-147">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="8c6c8-148">Introduzione alle query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-148">Introduction to LINQ Queries (C#)</span></span>](./introduction-to-linq-queries.md)
- [<span data-ttu-id="8c6c8-149">Sintassi di espressione di query per operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="8c6c8-149">Query Expression Syntax for Standard Query Operators (C#)</span></span>](./query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="8c6c8-150">Classificazione degli operatori di query standard in base alla modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8c6c8-150">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="8c6c8-151">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="8c6c8-151">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
