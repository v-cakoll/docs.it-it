---
title: 'Eccezioni: funzione raise (F#)'
description: Informazioni su come viene usata la funzione 'raise' di F# per indicare che si è verificato un errore o condizione eccezionale.
ms.date: 05/16/2016
ms.openlocfilehash: 537d274659d29404380bfdd56310ac267372bb98
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43778259"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="7c7f7-103">Eccezioni: funzione raise</span><span class="sxs-lookup"><span data-stu-id="7c7f7-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="7c7f7-104">Il `raise` funzione viene utilizzata per indicare che si è verificato un errore o condizione eccezionale.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="7c7f7-105">Informazioni sull'errore vengono acquisite in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c7f7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c7f7-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="7c7f7-107">Note</span><span class="sxs-lookup"><span data-stu-id="7c7f7-107">Remarks</span></span>

<span data-ttu-id="7c7f7-108">Il `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="7c7f7-109">Il processo di rimozione dello stack viene gestito da common language runtime (CLR), quindi il comportamento di questo processo è lo stesso perché si trova in qualsiasi altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="7c7f7-110">Il processo di rimozione dello stack è una ricerca per un gestore di eccezioni che corrisponde all'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="7c7f7-111">Viene avviata la ricerca nell'attuale `try...with` espressione, se presente.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="7c7f7-112">I modelli di `with` blocco è selezionato, nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="7c7f7-113">Quando viene trovato un gestore eccezioni corrispondente, l'eccezione viene considerata come gestito; in caso contrario, lo stack viene rimosso e `with` blocchi la catena di chiamate vengono controllati fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="7c7f7-114">Qualsiasi `finally` blocchi che si verificano nella catena di chiamate vengono anche eseguiti in sequenza come lo stack viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="7c7f7-115">Il `raise` funzione equivale a `throw` in c# o C++.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="7c7f7-116">Usare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="7c7f7-117">Gli esempi di codice seguenti illustrano l'uso del `raise` funzione per generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="7c7f7-118">Il `raise` funzione può essere usata anche per la generazione di eccezioni .NET, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7c7f7-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="7c7f7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c7f7-119">See also</span></span>

- [<span data-ttu-id="7c7f7-120">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="7c7f7-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="7c7f7-121">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="7c7f7-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="7c7f7-122">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="7c7f7-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="7c7f7-123">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="7c7f7-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="7c7f7-124">Eccezioni: funzione `failwith`</span><span class="sxs-lookup"><span data-stu-id="7c7f7-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="7c7f7-125">Eccezioni: funzione `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="7c7f7-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
