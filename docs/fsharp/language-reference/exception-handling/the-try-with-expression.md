---
title: 'Eccezioni: espressione try...with (F#)'
description: "Informazioni su come usare l'espressione 'try... con' di F # per la gestione delle eccezioni."
ms.date: 05/16/2016
ms.openlocfilehash: 588960c0f8ccedb431c37d0f1314bf1a293b638c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042166"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="11e1d-103">Eccezioni: espressione try...with</span><span class="sxs-lookup"><span data-stu-id="11e1d-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="11e1d-104">Questo argomento viene descritto il `try...with` espressione, l'espressione che viene usato per la gestione delle eccezioni nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="11e1d-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="11e1d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11e1d-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="11e1d-106">Note</span><span class="sxs-lookup"><span data-stu-id="11e1d-106">Remarks</span></span>

<span data-ttu-id="11e1d-107">Il `try...with` espressione viene usata per gestire le eccezioni in F #.</span><span class="sxs-lookup"><span data-stu-id="11e1d-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="11e1d-108">È simile al `try...catch` istruzione in c#.</span><span class="sxs-lookup"><span data-stu-id="11e1d-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="11e1d-109">Nella sintassi precedente, il codice nel *expression1* potrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="11e1d-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="11e1d-110">Il `try...with` espressione restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="11e1d-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="11e1d-111">Se viene generata alcuna eccezione, l'intera espressione restituisce il valore della *expression1*.</span><span class="sxs-lookup"><span data-stu-id="11e1d-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="11e1d-112">Se viene generata un'eccezione, ognuna *pattern* viene confrontato a sua volta con l'eccezione e per il primo modello corrisponda, corrispondente *expression*, noto come il *gestoredieccezioni*, per quel ramo viene eseguito e l'espressione globale restituisce il valore dell'espressione in tale gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="11e1d-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="11e1d-113">Se nessun criterio corrisponde, l'eccezione si propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="11e1d-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="11e1d-114">I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nella `try` blocco.</span><span class="sxs-lookup"><span data-stu-id="11e1d-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="11e1d-115">Spesso, il fatto che si verificato un errore anche significa che vi è alcun valore validi che può essere restituite dalle espressioni in ogni gestore eccezioni.</span><span class="sxs-lookup"><span data-stu-id="11e1d-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="11e1d-116">Un modello frequente consiste nell'avere il tipo dell'espressione sia un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="11e1d-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="11e1d-117">L'esempio di codice seguente illustra questo modello.</span><span class="sxs-lookup"><span data-stu-id="11e1d-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="11e1d-118">Le eccezioni possono essere le eccezioni .NET, o possono essere le eccezioni di F #.</span><span class="sxs-lookup"><span data-stu-id="11e1d-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="11e1d-119">È possibile definire eccezioni F # tramite la `exception` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="11e1d-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="11e1d-120">È possibile usare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e altre condizioni. Nella tabella seguente sono riepilogate le opzioni.</span><span class="sxs-lookup"><span data-stu-id="11e1d-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="11e1d-121">Modello</span><span class="sxs-lookup"><span data-stu-id="11e1d-121">Pattern</span></span>|<span data-ttu-id="11e1d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11e1d-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="11e1d-123">:?</span><span class="sxs-lookup"><span data-stu-id="11e1d-123">:?</span></span> <span data-ttu-id="11e1d-124">*tipo di eccezione*</span><span class="sxs-lookup"><span data-stu-id="11e1d-124">*exception-type*</span></span>|<span data-ttu-id="11e1d-125">Corrisponde al tipo di eccezione .NET specificato.</span><span class="sxs-lookup"><span data-stu-id="11e1d-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="11e1d-126">:?</span><span class="sxs-lookup"><span data-stu-id="11e1d-126">:?</span></span> <span data-ttu-id="11e1d-127">*tipo di eccezione* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="11e1d-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="11e1d-128">Corrisponde al tipo di eccezione .NET specificato, ma offre un valore denominato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="11e1d-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="11e1d-129">*nome dell'eccezione*(*argomenti*)</span><span class="sxs-lookup"><span data-stu-id="11e1d-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="11e1d-130">Corrisponde a un tipo di eccezione F # e associa gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="11e1d-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="11e1d-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="11e1d-131">*identifier*</span></span>|<span data-ttu-id="11e1d-132">Corrisponde a tutte le eccezioni e associa il nome dell'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="11e1d-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="11e1d-133">Equivalente a \**:? System. Exception come \* \* \* identificatore*</span><span class="sxs-lookup"><span data-stu-id="11e1d-133">Equivalent to \**:? System.Exception as\*\*\*identifier*</span></span>|
|<span data-ttu-id="11e1d-134">*Identificatore* quando *condizione*</span><span class="sxs-lookup"><span data-stu-id="11e1d-134">*identifier* when *condition*</span></span>|<span data-ttu-id="11e1d-135">Corrisponde a tutte le eccezioni se la condizione è true.</span><span class="sxs-lookup"><span data-stu-id="11e1d-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="11e1d-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="11e1d-136">Examples</span></span>

<span data-ttu-id="11e1d-137">Gli esempi di codice seguenti illustrano l'uso di vari modelli di gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="11e1d-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

>[!NOTE]
<span data-ttu-id="11e1d-138">Il `try...with` costrutto è un'espressione separata dal `try...finally` espressione.</span><span class="sxs-lookup"><span data-stu-id="11e1d-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="11e1d-139">Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario annidare le due espressioni.</span><span class="sxs-lookup"><span data-stu-id="11e1d-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE]
<span data-ttu-id="11e1d-140">È possibile usare `try...with` nei flussi di lavoro asincroni e altre espressioni di calcolo, in cui una versione personalizzata di case di `try...with` espressione viene usata.</span><span class="sxs-lookup"><span data-stu-id="11e1d-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="11e1d-141">Per altre informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md), e [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11e1d-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11e1d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11e1d-142">See also</span></span>

- [<span data-ttu-id="11e1d-143">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="11e1d-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="11e1d-144">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="11e1d-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="11e1d-145">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="11e1d-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
