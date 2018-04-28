---
title: 'Eccezioni: espressione try...finally (F#)'
description: "Informazioni su come F # ' try... finally' espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un'eccezione."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 588e4edb4d25c6d25ef103ba724613db997f68d7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="0d637-103">Eccezioni: espressione try...finally</span><span class="sxs-lookup"><span data-stu-id="0d637-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="0d637-104">Il `try...finally` espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d637-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="0d637-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d637-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="0d637-106">Note</span><span class="sxs-lookup"><span data-stu-id="0d637-106">Remarks</span></span>
<span data-ttu-id="0d637-107">Il `try...finally` espressione può essere utilizzata per eseguire il codice in *expression2* nella sintassi precedente, indipendentemente dal fatto che viene generata un'eccezione durante l'esecuzione di *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0d637-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="0d637-108">Il tipo di *expression2* non contribuiscono al valore dell'intera espressione; il tipo restituito quando non si verifica un'eccezione è l'ultimo valore in *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0d637-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="0d637-109">Quando si verifica un'eccezione, viene restituito alcun valore e il flusso di controllo trasferisce al gestore di eccezioni corrispondente successivo lo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="0d637-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="0d637-110">Se non viene trovato alcun gestore eccezioni, il programma termina.</span><span class="sxs-lookup"><span data-stu-id="0d637-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="0d637-111">Prima che venga eseguito il codice in un gestore corrispondente o il programma termina, il codice di `finally` ramo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d637-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="0d637-112">Il codice seguente illustra l'uso del `try...finally` espressione.</span><span class="sxs-lookup"><span data-stu-id="0d637-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="0d637-113">L'output alla console è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d637-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="0d637-114">Come si vede dall'output, il flusso è stato chiuso prima che è stata gestita l'eccezione esterna e il file `test.txt` contiene il testo `test1`, indica che i buffer sono stati scaricati e scritti su disco, anche se l'eccezione ha trasferito controllo al gestore dell'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="0d637-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="0d637-115">Si noti che il `try...with` costrutto è distinto dal costrutto di `try...finally` costruire.</span><span class="sxs-lookup"><span data-stu-id="0d637-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="0d637-116">Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario nidificare i due costrutti, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0d637-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="0d637-117">Nel contesto di espressioni di calcolo, incluse le espressioni di sequenza e flussi di lavoro asincroni **try... finally** espressioni possono avere un'implementazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0d637-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="0d637-118">Per ulteriori informazioni, vedere [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0d637-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="0d637-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d637-119">See Also</span></span>
[<span data-ttu-id="0d637-120">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="0d637-120">Exception Handling</span></span>](index.md)

[<span data-ttu-id="0d637-121">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="0d637-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
