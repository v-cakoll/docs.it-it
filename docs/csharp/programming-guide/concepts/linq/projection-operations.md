---
title: Operazioni di proiezione (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: f76eeeb779ab08a575e758a9d974573b700ae652
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168336"
---
# <a name="projection-operations-c"></a><span data-ttu-id="ffe49-102">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="ffe49-102">Projection Operations (C#)</span></span>
<span data-ttu-id="ffe49-103">La proiezione si riferisce all'operazione di trasformazione di un oggetto in un nuovo form costituito spesso solo dalle proprietà che verranno usate successivamente.</span><span class="sxs-lookup"><span data-stu-id="ffe49-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="ffe49-104">Utilizzando la proiezione, è possibile costruire un nuovo tipo compilato in base a ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="ffe49-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="ffe49-105">È possibile proiettare una proprietà ed eseguirvi una funzione matematica.</span><span class="sxs-lookup"><span data-stu-id="ffe49-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="ffe49-106">È anche possibile proiettare l'oggetto originale senza modificarlo.</span><span class="sxs-lookup"><span data-stu-id="ffe49-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="ffe49-107">Nella sezione seguente sono elencati i metodi dell'operatore query standard che eseguono la proiezione.</span><span class="sxs-lookup"><span data-stu-id="ffe49-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffe49-108">Metodi</span><span class="sxs-lookup"><span data-stu-id="ffe49-108">Methods</span></span>  
  
|<span data-ttu-id="ffe49-109">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="ffe49-109">Method Name</span></span>|<span data-ttu-id="ffe49-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffe49-110">Description</span></span>|<span data-ttu-id="ffe49-111">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="ffe49-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="ffe49-112">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ffe49-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ffe49-113">Select</span><span class="sxs-lookup"><span data-stu-id="ffe49-113">Select</span></span>|<span data-ttu-id="ffe49-114">Proietta i valori che si basano su una funzione di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="ffe49-114">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ffe49-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="ffe49-115">SelectMany</span></span>|<span data-ttu-id="ffe49-116">Proietta le sequenze di valori che si basano su una funzione di trasformazione semplificandoli in un'unica sequenza.</span><span class="sxs-lookup"><span data-stu-id="ffe49-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="ffe49-117">Usare più clausole `from`</span><span class="sxs-lookup"><span data-stu-id="ffe49-117">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ffe49-118">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ffe49-118">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="ffe49-119">Select</span><span class="sxs-lookup"><span data-stu-id="ffe49-119">Select</span></span>  
 <span data-ttu-id="ffe49-120">L'esempio seguente usa la clausola `select` per proiettare la prima lettera di ogni stringa di un elenco di stringhe.</span><span class="sxs-lookup"><span data-stu-id="ffe49-120">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="ffe49-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="ffe49-121">SelectMany</span></span>  
 <span data-ttu-id="ffe49-122">L'esempio seguente usa più clausole `from` per proiettare tutte le parole di ogni stringa di un elenco di stringhe.</span><span class="sxs-lookup"><span data-stu-id="ffe49-122">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="ffe49-123">Confronto tra Select e SelectMany</span><span class="sxs-lookup"><span data-stu-id="ffe49-123">Select versus SelectMany</span></span>  
 <span data-ttu-id="ffe49-124">La funzione di `Select()` e `SelectMany()` è produrre uno o più valori risultato dai valori di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="ffe49-125">`Select()` produce un valore risultato per ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="ffe49-126">Il risultato complessivo è pertanto una raccolta contenente lo stesso numero di elementi della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="ffe49-127">Al contrario, `SelectMany()` produce un singolo risultato complessivo che contiene sottoraccolte concatenate di ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="ffe49-128">La funzione di trasformazione passata come argomento a `SelectMany()` deve restituire una sequenza enumerabile di valori per ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="ffe49-129">Queste sequenze enumerabili vengono quindi concatenate da `SelectMany()` per creare un'unica grande sequenza.</span><span class="sxs-lookup"><span data-stu-id="ffe49-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="ffe49-130">Le due figure seguenti illustrano la differenza concettuale tra le azioni di questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="ffe49-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="ffe49-131">In ogni caso, si supponga che la funzione del selettore (trasformazione) selezioni la matrice di fiori di ogni valore di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="ffe49-132">La figura mostra che `Select()` restituisce una raccolta contenente lo stesso numero di elementi della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 ![Elemento grafico che illustra l'azione di Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 <span data-ttu-id="ffe49-134">La figura mostra che `SelectMany()` concatena la sequenza intermedia di matrici in un unico valore risultato finale contenente tutti i valori di ogni matrice intermedia.</span><span class="sxs-lookup"><span data-stu-id="ffe49-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 ![Elemento grafico che illustra l'azione di SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a><span data-ttu-id="ffe49-136">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="ffe49-136">Code Example</span></span>  
 <span data-ttu-id="ffe49-137">L'esempio seguente confronta il comportamento di `Select()` e `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="ffe49-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="ffe49-138">Il codice crea un "bouquet" di fiori prendendo i primi due elementi di ogni elenco di nomi di fiori nella raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="ffe49-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="ffe49-139">In questo esempio, il "valore singolo" usato dalla funzione di trasformazione <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> è anch'esso una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="ffe49-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="ffe49-140">Questo richiede il ciclo `foreach` aggiuntivo in modo da enumerare tutte le stringhe di ogni sottosequenza.</span><span class="sxs-lookup"><span data-stu-id="ffe49-140">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffe49-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffe49-141">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="ffe49-142">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="ffe49-142">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="ffe49-143">clausola select</span><span class="sxs-lookup"><span data-stu-id="ffe49-143">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
- [<span data-ttu-id="ffe49-144">Come popolare le raccolte di oggetti da più origini (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="ffe49-144">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="ffe49-145">Come dividere un file in molti file utilizzando i gruppi (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="ffe49-145">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
