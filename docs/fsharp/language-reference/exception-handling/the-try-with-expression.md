---
title: 'Eccezioni: Espressione try...with'
description: Informazioni su come usare il F# ' try... with ' espressione per la gestione delle eccezioni.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630256"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="3bd14-103">Eccezioni: Espressione try...with</span><span class="sxs-lookup"><span data-stu-id="3bd14-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="3bd14-104">In questo argomento viene `try...with` descritta l'espressione, che viene utilizzata per la gestione delle eccezioni F# nel linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3bd14-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="3bd14-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bd14-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="3bd14-106">Note</span><span class="sxs-lookup"><span data-stu-id="3bd14-106">Remarks</span></span>

<span data-ttu-id="3bd14-107">L' `try...with` espressione viene utilizzata per gestire le eccezioni F#in.</span><span class="sxs-lookup"><span data-stu-id="3bd14-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="3bd14-108">È simile all' `try...catch` istruzione in. C#</span><span class="sxs-lookup"><span data-stu-id="3bd14-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="3bd14-109">Nella sintassi precedente, il codice in *expression1* potrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="3bd14-110">L' `try...with` espressione restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="3bd14-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="3bd14-111">Se non viene generata alcuna eccezione, l'intera espressione restituisce il valore di *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3bd14-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="3bd14-112">Se viene generata un'eccezione, ogni *modello* viene confrontato a sua volta con l'eccezione e per il primo criterio di corrispondenza, viene eseguita l' *espressione*corrispondente, nota come *gestore di eccezioni*, per quel ramo e l'espressione complessiva Restituisce il valore dell'espressione nel gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3bd14-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="3bd14-113">Se non corrisponde alcun criterio, l'eccezione propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3bd14-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="3bd14-114">I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nel `try` blocco.</span><span class="sxs-lookup"><span data-stu-id="3bd14-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="3bd14-115">Spesso, il fatto che si è verificato un errore significa anche che non esiste alcun valore valido che può essere restituito dalle espressioni in ogni gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3bd14-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="3bd14-116">Un modello frequente consiste nel fare in modo che il tipo dell'espressione sia un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="3bd14-117">Questo modello è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3bd14-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="3bd14-118">Le eccezioni possono essere eccezioni .NET oppure possono essere F# eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3bd14-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="3bd14-119">È possibile definire F# le eccezioni tramite la `exception` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="3bd14-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="3bd14-120">È possibile usare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e ad altre condizioni; le opzioni sono riepilogate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3bd14-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="3bd14-121">Modello</span><span class="sxs-lookup"><span data-stu-id="3bd14-121">Pattern</span></span>|<span data-ttu-id="3bd14-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bd14-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="3bd14-123">:?</span><span class="sxs-lookup"><span data-stu-id="3bd14-123">:?</span></span> <span data-ttu-id="3bd14-124">*exception-type*</span><span class="sxs-lookup"><span data-stu-id="3bd14-124">*exception-type*</span></span>|<span data-ttu-id="3bd14-125">Corrisponde al tipo di eccezione .NET specificato.</span><span class="sxs-lookup"><span data-stu-id="3bd14-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="3bd14-126">:?</span><span class="sxs-lookup"><span data-stu-id="3bd14-126">:?</span></span> <span data-ttu-id="3bd14-127">*tipo di eccezione* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="3bd14-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="3bd14-128">Corrisponde al tipo di eccezione .NET specificato, ma restituisce un valore denominato all'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="3bd14-129">*nome eccezione* (*argomenti*)</span><span class="sxs-lookup"><span data-stu-id="3bd14-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="3bd14-130">Corrisponde a F# un tipo di eccezione e associa gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3bd14-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="3bd14-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="3bd14-131">*identifier*</span></span>|<span data-ttu-id="3bd14-132">Corrisponde a qualsiasi eccezione e associa il nome all'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="3bd14-133">Equivalente a **:? System. Exception come**_identificatore_</span><span class="sxs-lookup"><span data-stu-id="3bd14-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="3bd14-134">*identificatore* quando la *condizione*</span><span class="sxs-lookup"><span data-stu-id="3bd14-134">*identifier* when *condition*</span></span>|<span data-ttu-id="3bd14-135">Corrisponde a qualsiasi eccezione se la condizione è true.</span><span class="sxs-lookup"><span data-stu-id="3bd14-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="3bd14-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="3bd14-136">Examples</span></span>

<span data-ttu-id="3bd14-137">Negli esempi di codice seguenti viene illustrato l'utilizzo dei diversi modelli di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3bd14-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="3bd14-138">Il `try...with` costrutto è un'espressione separata `try...finally` dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="3bd14-139">Pertanto, se il codice richiede un `with` blocco e un `finally` blocco, sarà necessario nidificare le due espressioni.</span><span class="sxs-lookup"><span data-stu-id="3bd14-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="3bd14-140">È possibile utilizzare `try...with` in flussi di lavoro asincroni e altre espressioni `try...with` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bd14-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="3bd14-141">Per altre informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md)ed [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3bd14-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3bd14-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bd14-142">See also</span></span>

- [<span data-ttu-id="3bd14-143">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="3bd14-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="3bd14-144">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="3bd14-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="3bd14-145">Eccezioni: `try...finally` Espressione</span><span class="sxs-lookup"><span data-stu-id="3bd14-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
