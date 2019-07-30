---
title: 'Eccezioni: Espressione try...finally'
description: Scopri in che F# modo ' try... Infine, l'espressione consente di eseguire il codice di pulizia anche se un blocco di codice genera un'eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630280"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="3aa52-103">Eccezioni: Espressione try...finally</span><span class="sxs-lookup"><span data-stu-id="3aa52-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="3aa52-104">L' `try...finally` espressione consente di eseguire il codice di pulizia anche se un blocco di codice genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3aa52-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="3aa52-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aa52-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="3aa52-106">Note</span><span class="sxs-lookup"><span data-stu-id="3aa52-106">Remarks</span></span>

<span data-ttu-id="3aa52-107">L' `try...finally` espressione può essere usata per eseguire il codice in *expression2* nella sintassi precedente, indipendentemente dal fatto che venga generata un'eccezione durante l'esecuzione di *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3aa52-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="3aa52-108">Il tipo di *expression2* non contribuisce al valore dell'intera espressione. il tipo restituito quando non si verifica un'eccezione è l'ultimo valore in *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3aa52-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="3aa52-109">Quando si verifica un'eccezione, non viene restituito alcun valore e il flusso di controllo viene trasferito al gestore di eccezioni corrispondente successivo fino allo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="3aa52-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="3aa52-110">Se non viene trovato alcun gestore di eccezioni, il programma termina.</span><span class="sxs-lookup"><span data-stu-id="3aa52-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="3aa52-111">Prima di eseguire il codice in un gestore corrispondente o il programma termina, viene eseguito il codice nel `finally` ramo.</span><span class="sxs-lookup"><span data-stu-id="3aa52-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="3aa52-112">Nel codice seguente viene illustrato l'utilizzo dell' `try...finally` espressione.</span><span class="sxs-lookup"><span data-stu-id="3aa52-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="3aa52-113">Di seguito è riportato l'output della console.</span><span class="sxs-lookup"><span data-stu-id="3aa52-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="3aa52-114">Come si può notare dall'output, il flusso è stato chiuso prima che venisse gestita l'eccezione esterna e il file `test.txt` contiene il testo `test1`, che indica che i buffer sono stati scaricati e scritti su disco anche se l'eccezione è stata trasferita controllo al gestore di eccezioni esterno.</span><span class="sxs-lookup"><span data-stu-id="3aa52-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="3aa52-115">Si noti che `try...with` il costrutto è un costrutto `try...finally` separato dal costrutto.</span><span class="sxs-lookup"><span data-stu-id="3aa52-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="3aa52-116">Pertanto, se il codice richiede un `with` blocco e un `finally` blocco, è necessario annidare i due costrutti, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3aa52-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="3aa52-117">Nel contesto delle espressioni di calcolo, incluse le espressioni di sequenza e i flussi di lavoro asincroni, **provare...** le espressioni finally possono avere un'implementazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3aa52-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="3aa52-118">Per altre informazioni, vedere [espressioni di calcolo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3aa52-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3aa52-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aa52-119">See also</span></span>

- [<span data-ttu-id="3aa52-120">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="3aa52-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="3aa52-121">Eccezioni: `try...with` Espressione</span><span class="sxs-lookup"><span data-stu-id="3aa52-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
