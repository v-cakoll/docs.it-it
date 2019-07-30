---
title: 'Eccezioni: funzione raise'
description: Informazioni sul modo F# in cui viene usata la funzione ' raise ' per indicare che si è verificato un errore o una condizione eccezionale.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630293"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="c36a0-103">Eccezioni: funzione raise</span><span class="sxs-lookup"><span data-stu-id="c36a0-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="c36a0-104">La `raise` funzione viene usata per indicare che si è verificato un errore o una condizione eccezionale.</span><span class="sxs-lookup"><span data-stu-id="c36a0-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="c36a0-105">Le informazioni sull'errore vengono acquisite in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="c36a0-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="c36a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c36a0-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="c36a0-107">Note</span><span class="sxs-lookup"><span data-stu-id="c36a0-107">Remarks</span></span>

<span data-ttu-id="c36a0-108">La `raise` funzione genera un oggetto eccezione e avvia un processo di rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="c36a0-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="c36a0-109">Il processo di rimozione dello stack è gestito dal Common Language Runtime (CLR), quindi il comportamento di questo processo è identico a quello in qualsiasi altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="c36a0-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="c36a0-110">Il processo di rimozione dello stack è una ricerca di un gestore di eccezioni che corrisponde all'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="c36a0-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="c36a0-111">La ricerca inizia nell'espressione corrente `try...with` , se ne esiste una.</span><span class="sxs-lookup"><span data-stu-id="c36a0-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="c36a0-112">Ogni modello nel `with` blocco è selezionato, in ordine.</span><span class="sxs-lookup"><span data-stu-id="c36a0-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="c36a0-113">Quando viene trovato un gestore di eccezioni corrispondente, l'eccezione viene considerata gestita; in caso contrario, lo stack viene rimosso `with` e il blocco della catena di chiamate viene verificato fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c36a0-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="c36a0-114">Tutti `finally` i blocchi rilevati nella catena di chiamate vengono eseguiti anche in sequenza come rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="c36a0-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="c36a0-115">La `raise` funzione è l'equivalente di `throw` in C# o C++.</span><span class="sxs-lookup"><span data-stu-id="c36a0-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="c36a0-116">Utilizzare `reraise` in un gestore catch per propagare la stessa eccezione fino alla catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="c36a0-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="c36a0-117">Negli esempi di codice seguenti viene illustrato l'utilizzo della `raise` funzione per generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c36a0-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="c36a0-118">La `raise` funzione può essere utilizzata anche per generare eccezioni .NET, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c36a0-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="c36a0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c36a0-119">See also</span></span>

- [<span data-ttu-id="c36a0-120">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c36a0-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="c36a0-121">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="c36a0-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="c36a0-122">Eccezioni: `try...with` Espressione</span><span class="sxs-lookup"><span data-stu-id="c36a0-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="c36a0-123">Eccezioni: `try...finally` Espressione</span><span class="sxs-lookup"><span data-stu-id="c36a0-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="c36a0-124">Eccezioni: `failwith` Funzione</span><span class="sxs-lookup"><span data-stu-id="c36a0-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="c36a0-125">Eccezioni: `invalidArg` Funzione</span><span class="sxs-lookup"><span data-stu-id="c36a0-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
