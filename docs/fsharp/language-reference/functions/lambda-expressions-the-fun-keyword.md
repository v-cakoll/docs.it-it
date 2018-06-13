---
title: 'Espressioni lambda: parola chiave fun (F#)'
description: "Informazioni su come utilizzare la parola chiave 'fun' F # per definire un'espressione lambda, che è una funzione anonima."
ms.date: 05/16/2016
ms.openlocfilehash: 433451fb9bf89bfabdcd8e71560105317771d251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563850"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="a8977-103">Espressioni lambda: parola chiave fun (F#)</span><span class="sxs-lookup"><span data-stu-id="a8977-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="a8977-104">Il `fun` parola chiave viene utilizzata per definire un'espressione lambda, vale a dire, una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="a8977-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="a8977-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8977-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="a8977-106">Note</span><span class="sxs-lookup"><span data-stu-id="a8977-106">Remarks</span></span>
<span data-ttu-id="a8977-107">Il *elenco di parametri* consiste in genere di nomi e, facoltativamente, tipi di parametri.</span><span class="sxs-lookup"><span data-stu-id="a8977-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="a8977-108">Più in generale, il *elenco di parametri* può essere composto da qualsiasi modello F #.</span><span class="sxs-lookup"><span data-stu-id="a8977-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="a8977-109">Per un elenco completo di modelli possibili, vedere [criteri di ricerca](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="a8977-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="a8977-110">Elenchi di parametri validi includono i seguenti esempi.</span><span class="sxs-lookup"><span data-stu-id="a8977-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="a8977-111">Il *espressione* è il corpo della funzione, di cui l'ultima espressione genera un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="a8977-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="a8977-112">Esempi di espressioni lambda validi includono:</span><span class="sxs-lookup"><span data-stu-id="a8977-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="a8977-113">Uso di espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="a8977-113">Using Lambda Expressions</span></span>
<span data-ttu-id="a8977-114">Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare il lavoro aggiuntivo della definizione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="a8977-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="a8977-115">Molte funzioni della libreria F # accettano valori di funzione come argomenti e può risultare particolarmente utile utilizzare un'espressione lambda in questi casi.</span><span class="sxs-lookup"><span data-stu-id="a8977-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="a8977-116">Il codice seguente si applica un'espressione lambda a elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="a8977-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="a8977-117">In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="a8977-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a8977-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8977-118">See Also</span></span>
[<span data-ttu-id="a8977-119">Funzioni</span><span class="sxs-lookup"><span data-stu-id="a8977-119">Functions</span></span>](index.md)
