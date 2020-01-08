---
title: Funzioni definite dall'utente
ms.date: 12/13/2019
description: Informazioni su come creare funzioni scalari e di aggregazione definite dall'utente.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447174"
---
# <a name="user-defined-functions"></a><span data-ttu-id="f61c9-103">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f61c9-103">User-defined functions</span></span>

<span data-ttu-id="f61c9-104">La maggior parte dei database ha un sottolinguaggio procedurale di SQL che è possibile usare per definire funzioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f61c9-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="f61c9-105">SQLite, tuttavia, viene eseguito in-process con l'app.</span><span class="sxs-lookup"><span data-stu-id="f61c9-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="f61c9-106">Anziché dover apprendere un nuovo dialetto di SQL, è possibile usare semplicemente il linguaggio di programmazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="f61c9-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="f61c9-107">Funzioni scalari</span><span class="sxs-lookup"><span data-stu-id="f61c9-107">Scalar functions</span></span>

<span data-ttu-id="f61c9-108">Le funzioni scalari restituiscono un singolo valore scalare per ogni riga di una query.</span><span class="sxs-lookup"><span data-stu-id="f61c9-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="f61c9-109">Definire nuove funzioni scalari ed eseguire l'override di quelle predefinite usando <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span><span class="sxs-lookup"><span data-stu-id="f61c9-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="f61c9-110">Per un elenco di parametri e tipi restituiti supportati per l'argomento `func`, vedere [tipi di dati](types.md) .</span><span class="sxs-lookup"><span data-stu-id="f61c9-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="f61c9-111">Se si specifica l'argomento `state`, il valore passerà a ogni chiamata della funzione.</span><span class="sxs-lookup"><span data-stu-id="f61c9-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="f61c9-112">Usare questa operazione per evitare chiusure.</span><span class="sxs-lookup"><span data-stu-id="f61c9-112">Use this to avoid closures.</span></span>

<span data-ttu-id="f61c9-113">Specificare `isDeterministic` se la funzione è deterministica per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="f61c9-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="f61c9-114">Nell'esempio seguente viene illustrato come aggiungere una funzione scalare per calcolare il raggio di un cilindro.</span><span class="sxs-lookup"><span data-stu-id="f61c9-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="f61c9-115">Operatori</span><span class="sxs-lookup"><span data-stu-id="f61c9-115">Operators</span></span>

<span data-ttu-id="f61c9-116">Gli operatori SQLite seguenti vengono implementati dalle funzioni scalari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f61c9-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="f61c9-117">La definizione di queste funzioni scalari nell'app sostituirà il comportamento di questi operatori.</span><span class="sxs-lookup"><span data-stu-id="f61c9-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="f61c9-118">??</span><span class="sxs-lookup"><span data-stu-id="f61c9-118">Operator</span></span>          | <span data-ttu-id="f61c9-119">Funzione</span><span class="sxs-lookup"><span data-stu-id="f61c9-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="f61c9-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="f61c9-120">X GLOB Y</span></span>          | <span data-ttu-id="f61c9-121">Glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="f61c9-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="f61c9-122">X COME Y</span><span class="sxs-lookup"><span data-stu-id="f61c9-122">X LIKE Y</span></span>          | <span data-ttu-id="f61c9-123">like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="f61c9-123">like(Y, X)</span></span>    |
| <span data-ttu-id="f61c9-124">X COME ESCAPE Y Z</span><span class="sxs-lookup"><span data-stu-id="f61c9-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="f61c9-125">like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="f61c9-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="f61c9-126">X CORRISPONDENZA Y</span><span class="sxs-lookup"><span data-stu-id="f61c9-126">X MATCH Y</span></span>         | <span data-ttu-id="f61c9-127">Match (Y, X)</span><span class="sxs-lookup"><span data-stu-id="f61c9-127">match(Y, X)</span></span>   |
| <span data-ttu-id="f61c9-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="f61c9-128">X REGEXP Y</span></span>        | <span data-ttu-id="f61c9-129">RegExp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="f61c9-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="f61c9-130">Nell'esempio seguente viene illustrato come definire la funzione regexp per abilitare l'operatore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f61c9-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="f61c9-131">SQLite non include un'implementazione predefinita della funzione RegExp.</span><span class="sxs-lookup"><span data-stu-id="f61c9-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="f61c9-132">Funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="f61c9-132">Aggregate functions</span></span>

<span data-ttu-id="f61c9-133">Le funzioni di aggregazione restituiscono un singolo valore aggregato per tutte le righe di una query.</span><span class="sxs-lookup"><span data-stu-id="f61c9-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="f61c9-134">Definire ed eseguire l'override di funzioni di aggregazione utilizzando <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f61c9-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="f61c9-135">L'argomento `seed` specifica lo stato iniziale del contesto.</span><span class="sxs-lookup"><span data-stu-id="f61c9-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="f61c9-136">Usare questo per evitare anche le chiusure.</span><span class="sxs-lookup"><span data-stu-id="f61c9-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="f61c9-137">L'argomento `func` viene richiamato una volta per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="f61c9-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="f61c9-138">Usare il contesto per accumulare un risultato finale.</span><span class="sxs-lookup"><span data-stu-id="f61c9-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="f61c9-139">Restituisce il contesto.</span><span class="sxs-lookup"><span data-stu-id="f61c9-139">Return the context.</span></span> <span data-ttu-id="f61c9-140">Questo modello consente al contesto di essere un tipo valore o non modificabile.</span><span class="sxs-lookup"><span data-stu-id="f61c9-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="f61c9-141">Se non viene specificato alcun `resultSelector`, come risultato viene utilizzato lo stato finale del contesto.</span><span class="sxs-lookup"><span data-stu-id="f61c9-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="f61c9-142">Ciò consente di semplificare la definizione di funzioni quali SUM e count che devono solo incrementare un numero ogni riga e restituirla.</span><span class="sxs-lookup"><span data-stu-id="f61c9-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="f61c9-143">Specificare `resultSelector` per calcolare il risultato finale dal contesto dopo l'iterazione in tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="f61c9-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="f61c9-144">Per un elenco dei tipi di parametro supportati per l'argomento `func` e i tipi restituiti per `resultSelector`, vedere [tipi di dati](types.md) .</span><span class="sxs-lookup"><span data-stu-id="f61c9-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="f61c9-145">Se la funzione è deterministica, specificare `isDeterministic` per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="f61c9-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="f61c9-146">Nell'esempio seguente viene definita una funzione di aggregazione per calcolare la deviazione standard di una colonna.</span><span class="sxs-lookup"><span data-stu-id="f61c9-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="f61c9-147">Errori di</span><span class="sxs-lookup"><span data-stu-id="f61c9-147">Errors</span></span>

<span data-ttu-id="f61c9-148">Se una funzione definita dall'utente genera un'eccezione, il messaggio viene restituito a SQLite.</span><span class="sxs-lookup"><span data-stu-id="f61c9-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="f61c9-149">SQLite genera quindi un errore e Microsoft. Data. sqlite genererà una Sqliteexception.</span><span class="sxs-lookup"><span data-stu-id="f61c9-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="f61c9-150">Per ulteriori informazioni, vedere [errori del database](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="f61c9-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="f61c9-151">Per impostazione predefinita, il codice di errore SQLite di errore verrà SQLITE_ERROR (o 1).</span><span class="sxs-lookup"><span data-stu-id="f61c9-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="f61c9-152">È tuttavia possibile modificarlo generando un <xref:Microsoft.Data.Sqlite.SqliteException> nella funzione con la <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> desiderata specificata.</span><span class="sxs-lookup"><span data-stu-id="f61c9-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="f61c9-153">Debug</span><span class="sxs-lookup"><span data-stu-id="f61c9-153">Debugging</span></span>

<span data-ttu-id="f61c9-154">SQLite chiama direttamente l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f61c9-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="f61c9-155">Ciò consente di aggiungere punti di interruzione che si attivano mentre SQLite sta valutando le query.</span><span class="sxs-lookup"><span data-stu-id="f61c9-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="f61c9-156">L'esperienza di debug .NET completa è disponibile per semplificare la creazione di funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f61c9-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f61c9-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f61c9-157">See also</span></span>

* [<span data-ttu-id="f61c9-158">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="f61c9-158">Data types</span></span>](types.md)
* [<span data-ttu-id="f61c9-159">Funzioni di base di SQLite</span><span class="sxs-lookup"><span data-stu-id="f61c9-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="f61c9-160">Funzioni di aggregazione SQLite</span><span class="sxs-lookup"><span data-stu-id="f61c9-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
