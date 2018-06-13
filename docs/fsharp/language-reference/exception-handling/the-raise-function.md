---
title: 'Eccezioni: funzione raise (F#)'
description: "Informazioni su come la funzione F # 'raise' viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale."
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564753"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="61a85-103">Eccezioni: funzione raise</span><span class="sxs-lookup"><span data-stu-id="61a85-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="61a85-104">Il `raise` funzione viene utilizzata per indicare che si è verificato un errore o una condizione eccezionale.</span><span class="sxs-lookup"><span data-stu-id="61a85-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="61a85-105">Informazioni sull'errore vengono acquisite in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="61a85-105">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="61a85-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61a85-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="61a85-107">Note</span><span class="sxs-lookup"><span data-stu-id="61a85-107">Remarks</span></span>
<span data-ttu-id="61a85-108">Il `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione di stack.</span><span class="sxs-lookup"><span data-stu-id="61a85-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="61a85-109">Il processo di rimozione dello stack è gestito da common language runtime (CLR), pertanto il comportamento di questo processo è lo stesso come in qualsiasi altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="61a85-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="61a85-110">Il processo di rimozione dello stack è una ricerca di un gestore di eccezioni che corrisponde all'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="61a85-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="61a85-111">La ricerca inizia in corrente `try...with` espressione, se presente.</span><span class="sxs-lookup"><span data-stu-id="61a85-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="61a85-112">Ogni modello nel `with` blocco è selezionato, nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61a85-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="61a85-113">Quando viene trovato un gestore eccezioni corrispondente, l'eccezione viene considerata gestita. in caso contrario, lo stack viene rimosso e `with` blocchi la catena di chiamate vengono controllati fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="61a85-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="61a85-114">Qualsiasi `finally` blocchi che vengono rilevati nella catena di chiamate vengono inoltre eseguiti in sequenza come lo stack viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="61a85-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="61a85-115">Il `raise` funzione equivale a `throw` in c# o C++.</span><span class="sxs-lookup"><span data-stu-id="61a85-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="61a85-116">Utilizzare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="61a85-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="61a85-117">Gli esempi di codice seguente viene illustrato l'utilizzo del `raise` funzione genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="61a85-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="61a85-118">Il `raise` funzione nonché per la generazione di eccezioni .NET, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="61a85-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="61a85-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a85-119">See Also</span></span>
[<span data-ttu-id="61a85-120">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="61a85-120">Exception Handling</span></span>](index.md)

[<span data-ttu-id="61a85-121">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="61a85-121">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="61a85-122">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="61a85-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="61a85-123">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="61a85-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="61a85-124">Eccezioni: funzione `failwith`</span><span class="sxs-lookup"><span data-stu-id="61a85-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="61a85-125">Eccezioni: funzione `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="61a85-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
