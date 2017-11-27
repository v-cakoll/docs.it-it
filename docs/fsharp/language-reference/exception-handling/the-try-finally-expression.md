---
title: 'Eccezioni: espressione try...finally (F#)'
description: 'Informazioni su come F # '' try... finally'' espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un''eccezione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="0a53c-104">Eccezioni: espressione try...finally</span><span class="sxs-lookup"><span data-stu-id="0a53c-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="0a53c-105">Il `try...finally` espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0a53c-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="0a53c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a53c-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="0a53c-107">Note</span><span class="sxs-lookup"><span data-stu-id="0a53c-107">Remarks</span></span>
<span data-ttu-id="0a53c-108">Il `try...finally` espressione può essere utilizzata per eseguire il codice in *expression2* nella sintassi precedente, indipendentemente dal fatto che viene generata un'eccezione durante l'esecuzione di *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0a53c-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="0a53c-109">Il tipo di *expression2* non contribuiscono al valore dell'intera espressione; il tipo restituito quando non si verifica un'eccezione è l'ultimo valore in *expression1*.</span><span class="sxs-lookup"><span data-stu-id="0a53c-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="0a53c-110">Quando si verifica un'eccezione, viene restituito alcun valore e il flusso di controllo trasferisce al gestore di eccezioni corrispondente successivo lo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="0a53c-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="0a53c-111">Se non viene trovato alcun gestore eccezioni, il programma termina.</span><span class="sxs-lookup"><span data-stu-id="0a53c-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="0a53c-112">Prima che venga eseguito il codice in un gestore corrispondente o il programma termina, il codice di `finally` ramo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0a53c-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="0a53c-113">Il codice seguente illustra l'uso del `try...finally` espressione.</span><span class="sxs-lookup"><span data-stu-id="0a53c-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="0a53c-114">L'output alla console è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0a53c-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="0a53c-115">Come si vede dall'output, il flusso è stato chiuso prima che è stata gestita l'eccezione esterna e il file `test.txt` contiene il testo `test1`, indica che i buffer sono stati scaricati e scritti su disco, anche se l'eccezione ha trasferito controllo al gestore dell'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="0a53c-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="0a53c-116">Si noti che il `try...with` costrutto è distinto dal costrutto di `try...finally` costruire.</span><span class="sxs-lookup"><span data-stu-id="0a53c-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="0a53c-117">Pertanto, se il codice richiede sia un `with` blocco e un `finally` blocco, è necessario nidificare i due costrutti, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0a53c-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="0a53c-118">Nel contesto di espressioni di calcolo, incluse le espressioni di sequenza e flussi di lavoro asincroni **try... finally** espressioni possono avere un'implementazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0a53c-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="0a53c-119">Per ulteriori informazioni, vedere [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0a53c-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="0a53c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a53c-120">See Also</span></span>
[<span data-ttu-id="0a53c-121">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="0a53c-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="0a53c-122">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="0a53c-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
