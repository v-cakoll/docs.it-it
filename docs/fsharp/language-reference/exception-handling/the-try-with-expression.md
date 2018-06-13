---
title: 'Eccezioni: espressione try...with (F#)'
description: "Informazioni su come utilizzare l'espressione 'try... with' di F # per la gestione delle eccezioni."
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565288"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="9a552-103">Eccezioni: espressione try...with</span><span class="sxs-lookup"><span data-stu-id="9a552-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="9a552-104">Questo argomento viene descritto il `try...with` expression, l'espressione che viene utilizzato per la gestione delle eccezioni nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="9a552-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="9a552-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a552-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="9a552-106">Note</span><span class="sxs-lookup"><span data-stu-id="9a552-106">Remarks</span></span>
<span data-ttu-id="9a552-107">Il `try...with` espressione viene utilizzata per gestire le eccezioni in F #.</span><span class="sxs-lookup"><span data-stu-id="9a552-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="9a552-108">È simile al `try...catch` istruzione in c#.</span><span class="sxs-lookup"><span data-stu-id="9a552-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="9a552-109">Nella sintassi precedente, il codice in *expression1* potrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9a552-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="9a552-110">Il `try...with` espressione restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="9a552-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="9a552-111">Se viene generata alcuna eccezione, l'intera espressione restituisce il valore di *expression1*.</span><span class="sxs-lookup"><span data-stu-id="9a552-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="9a552-112">Se viene generata un'eccezione, ogni *modello* viene confrontato a sua volta con l'eccezione e per il primo modello corrispondente, corrispondente *espressione*, noti come il *gestoredieccezioni*per tale branch viene eseguita e l'espressione complessiva restituisce il valore dell'espressione in tale gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9a552-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="9a552-113">Se non corrisponde alcun modello, l'eccezione si propaga lo stack di chiamate fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9a552-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="9a552-114">I tipi dei valori restituiti da ogni espressione nei gestori di eccezioni devono corrispondere al tipo restituito dall'espressione nel `try` blocco.</span><span class="sxs-lookup"><span data-stu-id="9a552-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="9a552-115">Il fatto che si verificato un errore anche spesso significa che è presente alcun valore valido che può essere restituito da espressioni in ogni gestore eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9a552-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="9a552-116">Un motivo frequente è che il tipo dell'espressione di essere un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="9a552-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="9a552-117">Esempio di codice seguente viene illustrato questo modello.</span><span class="sxs-lookup"><span data-stu-id="9a552-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="9a552-118">Le eccezioni possono essere eccezioni .NET, o possono essere eccezioni F #.</span><span class="sxs-lookup"><span data-stu-id="9a552-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="9a552-119">È possibile definire eccezioni F # utilizzando il `exception` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="9a552-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="9a552-120">È possibile utilizzare un'ampia gamma di modelli per filtrare in base al tipo di eccezione e altre condizioni. le opzioni sono riepilogate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9a552-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="9a552-121">Modello</span><span class="sxs-lookup"><span data-stu-id="9a552-121">Pattern</span></span>|<span data-ttu-id="9a552-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a552-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="9a552-123">:?</span><span class="sxs-lookup"><span data-stu-id="9a552-123">:?</span></span> <span data-ttu-id="9a552-124">*tipo di eccezione*</span><span class="sxs-lookup"><span data-stu-id="9a552-124">*exception-type*</span></span>|<span data-ttu-id="9a552-125">Corrisponde al tipo di eccezione .NET specificato.</span><span class="sxs-lookup"><span data-stu-id="9a552-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="9a552-126">:?</span><span class="sxs-lookup"><span data-stu-id="9a552-126">:?</span></span> <span data-ttu-id="9a552-127">*tipo di eccezione* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="9a552-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="9a552-128">Corrisponde al tipo di eccezione .NET specificato, ma consente l'eccezione di un valore denominato.</span><span class="sxs-lookup"><span data-stu-id="9a552-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="9a552-129">*nome di eccezione*(*argomenti*)</span><span class="sxs-lookup"><span data-stu-id="9a552-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="9a552-130">Corrisponde a un tipo di eccezione F # e associa gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="9a552-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="9a552-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="9a552-131">*identifier*</span></span>|<span data-ttu-id="9a552-132">Corrisponde a qualsiasi eccezione e associa il nome dell'oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="9a552-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="9a552-133">Equivalente a **:? System. Exception come * * * identificatore*</span><span class="sxs-lookup"><span data-stu-id="9a552-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="9a552-134">*Identificatore* quando *condizione*</span><span class="sxs-lookup"><span data-stu-id="9a552-134">*identifier* when *condition*</span></span>|<span data-ttu-id="9a552-135">Consente di ricercare qualsiasi eccezione se la condizione è true.</span><span class="sxs-lookup"><span data-stu-id="9a552-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="9a552-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="9a552-136">Examples</span></span>
<span data-ttu-id="9a552-137">Gli esempi di codice seguente viene illustrato l'utilizzo di vari modelli di gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9a552-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="9a552-138">Il `try...with` costrutto è un'espressione separata dal `try...finally` espressione.</span><span class="sxs-lookup"><span data-stu-id="9a552-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="9a552-139">Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario nidificare le due espressioni.</span><span class="sxs-lookup"><span data-stu-id="9a552-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="9a552-140">È possibile utilizzare `try...with` in flussi di lavoro asincroni e altre espressioni di calcolo, in cui una versione personalizzata di caso di `try...with` viene utilizzata l'espressione.</span><span class="sxs-lookup"><span data-stu-id="9a552-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="9a552-141">Per ulteriori informazioni, vedere [flussi di lavoro asincroni](../asynchronous-workflows.md), e [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9a552-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="9a552-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a552-142">See Also</span></span>
[<span data-ttu-id="9a552-143">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="9a552-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="9a552-144">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="9a552-144">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="9a552-145">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="9a552-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
