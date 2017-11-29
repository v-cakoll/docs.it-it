---
title: 'Eccezioni: funzione raise (F#)'
description: "Informazioni su come la funzione F # 'raise' viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="c6607-104">Eccezioni: funzione raise</span><span class="sxs-lookup"><span data-stu-id="c6607-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="c6607-105">Il `raise` funzione viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale.</span><span class="sxs-lookup"><span data-stu-id="c6607-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="c6607-106">Informazioni sull'errore vengono acquisite in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="c6607-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="c6607-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6607-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="c6607-108">Note</span><span class="sxs-lookup"><span data-stu-id="c6607-108">Remarks</span></span>
<span data-ttu-id="c6607-109">Il `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione di stack.</span><span class="sxs-lookup"><span data-stu-id="c6607-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="c6607-110">Il processo di rimozione dello stack è gestito da common language runtime (CLR), pertanto il comportamento di questo processo è lo stesso come in qualsiasi altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="c6607-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="c6607-111">Il processo di rimozione dello stack è una ricerca di un gestore di eccezioni che corrisponde all'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="c6607-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="c6607-112">La ricerca inizia in corrente `try...with` espressione, se presente.</span><span class="sxs-lookup"><span data-stu-id="c6607-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="c6607-113">Ogni modello nel `with` blocco è selezionato, nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c6607-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="c6607-114">Quando viene trovato un gestore eccezioni corrispondente, l'eccezione viene considerata gestita. in caso contrario, lo stack viene rimosso e `with` blocchi la catena di chiamate vengono controllati fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c6607-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="c6607-115">Qualsiasi `finally` blocchi che vengono rilevati nella catena di chiamate vengono inoltre eseguiti in sequenza come lo stack viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="c6607-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="c6607-116">Il `raise` funzione equivale a `throw` in c# o C++.</span><span class="sxs-lookup"><span data-stu-id="c6607-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="c6607-117">Utilizzare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6607-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="c6607-118">Gli esempi di codice seguente viene illustrato l'utilizzo del `raise` funzione genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c6607-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="c6607-119">Il `raise` funzione nonché per la generazione di eccezioni .NET, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c6607-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="c6607-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6607-120">See Also</span></span>
[<span data-ttu-id="c6607-121">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c6607-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="c6607-122">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="c6607-122">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="c6607-123">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="c6607-123">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="c6607-124">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="c6607-124">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="c6607-125">Eccezioni: funzione `failwith`</span><span class="sxs-lookup"><span data-stu-id="c6607-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="c6607-126">Eccezioni: funzione `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="c6607-126">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
