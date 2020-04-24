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
# <a name="user-defined-functions"></a><span data-ttu-id="987c6-103">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="987c6-103">User-defined functions</span></span>

<span data-ttu-id="987c6-104">La maggior parte dei database ha un sottolinguaggio procedurale di SQL che è possibile usare per definire funzioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="987c6-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="987c6-105">SQLite, tuttavia, viene eseguito in-process con l'app.</span><span class="sxs-lookup"><span data-stu-id="987c6-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="987c6-106">Anziché dover apprendere un nuovo dialetto di SQL, è possibile usare semplicemente il linguaggio di programmazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="987c6-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="987c6-107">Funzioni scalari</span><span class="sxs-lookup"><span data-stu-id="987c6-107">Scalar functions</span></span>

<span data-ttu-id="987c6-108">Le funzioni scalari restituiscono un singolo valore scalare per ogni riga di una query.</span><span class="sxs-lookup"><span data-stu-id="987c6-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="987c6-109">Definire nuove funzioni scalari ed eseguire l'override di quelle predefinite <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>usando.</span><span class="sxs-lookup"><span data-stu-id="987c6-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="987c6-110">Per [Data types](types.md) un elenco di parametri e tipi restituiti supportati per l' `func` argomento, vedere tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="987c6-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="987c6-111">Se si `state` specifica l'argomento, il valore passerà a ogni chiamata della funzione.</span><span class="sxs-lookup"><span data-stu-id="987c6-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="987c6-112">Usare questa operazione per evitare chiusure.</span><span class="sxs-lookup"><span data-stu-id="987c6-112">Use this to avoid closures.</span></span>

<span data-ttu-id="987c6-113">Specificare `isDeterministic` se la funzione è deterministica per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="987c6-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="987c6-114">Nell'esempio seguente viene illustrato come aggiungere una funzione scalare per calcolare il raggio di un cilindro.</span><span class="sxs-lookup"><span data-stu-id="987c6-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="987c6-115">Operatori</span><span class="sxs-lookup"><span data-stu-id="987c6-115">Operators</span></span>

<span data-ttu-id="987c6-116">Gli operatori SQLite seguenti vengono implementati dalle funzioni scalari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="987c6-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="987c6-117">La definizione di queste funzioni scalari nell'app sostituirà il comportamento di questi operatori.</span><span class="sxs-lookup"><span data-stu-id="987c6-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="987c6-118">Operatore</span><span class="sxs-lookup"><span data-stu-id="987c6-118">Operator</span></span>          | <span data-ttu-id="987c6-119">Funzione</span><span class="sxs-lookup"><span data-stu-id="987c6-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="987c6-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="987c6-120">X GLOB Y</span></span>          | <span data-ttu-id="987c6-121">Glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="987c6-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="987c6-122">X COME Y</span><span class="sxs-lookup"><span data-stu-id="987c6-122">X LIKE Y</span></span>          | <span data-ttu-id="987c6-123">like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="987c6-123">like(Y, X)</span></span>    |
| <span data-ttu-id="987c6-124">X COME ESCAPE Y Z</span><span class="sxs-lookup"><span data-stu-id="987c6-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="987c6-125">like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="987c6-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="987c6-126">X CORRISPONDENZA Y</span><span class="sxs-lookup"><span data-stu-id="987c6-126">X MATCH Y</span></span>         | <span data-ttu-id="987c6-127">Match (Y, X)</span><span class="sxs-lookup"><span data-stu-id="987c6-127">match(Y, X)</span></span>   |
| <span data-ttu-id="987c6-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="987c6-128">X REGEXP Y</span></span>        | <span data-ttu-id="987c6-129">RegExp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="987c6-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="987c6-130">Nell'esempio seguente viene illustrato come definire la funzione regexp per abilitare l'operatore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="987c6-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="987c6-131">SQLite non include un'implementazione predefinita della funzione RegExp.</span><span class="sxs-lookup"><span data-stu-id="987c6-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="987c6-132">Funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="987c6-132">Aggregate functions</span></span>

<span data-ttu-id="987c6-133">Le funzioni di aggregazione restituiscono un singolo valore aggregato per tutte le righe di una query.</span><span class="sxs-lookup"><span data-stu-id="987c6-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="987c6-134">Definire ed eseguire l'override di <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>funzioni di aggregazione tramite.</span><span class="sxs-lookup"><span data-stu-id="987c6-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="987c6-135">L' `seed` argomento specifica lo stato iniziale del contesto.</span><span class="sxs-lookup"><span data-stu-id="987c6-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="987c6-136">Usare questo per evitare anche le chiusure.</span><span class="sxs-lookup"><span data-stu-id="987c6-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="987c6-137">L' `func` argomento viene richiamato una volta per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="987c6-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="987c6-138">Usare il contesto per accumulare un risultato finale.</span><span class="sxs-lookup"><span data-stu-id="987c6-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="987c6-139">Restituisce il contesto.</span><span class="sxs-lookup"><span data-stu-id="987c6-139">Return the context.</span></span> <span data-ttu-id="987c6-140">Questo modello consente al contesto di essere un tipo valore o non modificabile.</span><span class="sxs-lookup"><span data-stu-id="987c6-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="987c6-141">Se non `resultSelector` si specifica alcun oggetto, viene utilizzato lo stato finale del contesto come risultato.</span><span class="sxs-lookup"><span data-stu-id="987c6-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="987c6-142">Ciò consente di semplificare la definizione di funzioni quali SUM e count che devono solo incrementare un numero ogni riga e restituirla.</span><span class="sxs-lookup"><span data-stu-id="987c6-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="987c6-143">Specificare `resultSelector` per calcolare il risultato finale dal contesto dopo l'iterazione in tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="987c6-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="987c6-144">Per [Data types](types.md) un elenco dei tipi di parametro supportati per l'argomento e `func` i tipi restituiti per `resultSelector`, vedere tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="987c6-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="987c6-145">Se la funzione è deterministica, `isDeterministic` specificare per consentire a SQLite di usare ottimizzazioni aggiuntive durante la compilazione delle query.</span><span class="sxs-lookup"><span data-stu-id="987c6-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="987c6-146">Nell'esempio seguente viene definita una funzione di aggregazione per calcolare la deviazione standard di una colonna.</span><span class="sxs-lookup"><span data-stu-id="987c6-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="987c6-147">Errors</span><span class="sxs-lookup"><span data-stu-id="987c6-147">Errors</span></span>

<span data-ttu-id="987c6-148">Se una funzione definita dall'utente genera un'eccezione, il messaggio viene restituito a SQLite.</span><span class="sxs-lookup"><span data-stu-id="987c6-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="987c6-149">SQLite genera quindi un errore e Microsoft. Data. sqlite genererà una Sqliteexception.</span><span class="sxs-lookup"><span data-stu-id="987c6-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="987c6-150">Per ulteriori informazioni, vedere [errori del database](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="987c6-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="987c6-151">Per impostazione predefinita, il codice di errore SQLite di errore verrà SQLITE_ERROR (o 1).</span><span class="sxs-lookup"><span data-stu-id="987c6-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="987c6-152">È tuttavia possibile modificarlo generando un oggetto <xref:Microsoft.Data.Sqlite.SqliteException> nella funzione con l'oggetto desiderato. <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode></span><span class="sxs-lookup"><span data-stu-id="987c6-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="987c6-153">Debug</span><span class="sxs-lookup"><span data-stu-id="987c6-153">Debugging</span></span>

<span data-ttu-id="987c6-154">SQLite chiama direttamente l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="987c6-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="987c6-155">Ciò consente di aggiungere punti di interruzione che si attivano mentre SQLite sta valutando le query.</span><span class="sxs-lookup"><span data-stu-id="987c6-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="987c6-156">L'esperienza di debug .NET completa è disponibile per semplificare la creazione di funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="987c6-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="987c6-157">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="987c6-157">See also</span></span>

* [<span data-ttu-id="987c6-158">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="987c6-158">Data types</span></span>](types.md)
* [<span data-ttu-id="987c6-159">Funzioni di base di SQLite</span><span class="sxs-lookup"><span data-stu-id="987c6-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="987c6-160">Funzioni di aggregazione SQLite</span><span class="sxs-lookup"><span data-stu-id="987c6-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
