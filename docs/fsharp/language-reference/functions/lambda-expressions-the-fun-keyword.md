---
title: 'Espressioni lambda: parola chiave fun (F#)'
description: "Informazioni su come utilizzare la parola chiave 'fun' F # per definire un'espressione lambda, che è una funzione anonima."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="5fe15-104">Espressioni lambda: parola chiave fun (F#)</span><span class="sxs-lookup"><span data-stu-id="5fe15-104">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="5fe15-105">Il `fun` parola chiave viene utilizzata per definire un'espressione lambda, vale a dire, una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="5fe15-105">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="5fe15-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fe15-106">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="5fe15-107">Note</span><span class="sxs-lookup"><span data-stu-id="5fe15-107">Remarks</span></span>
<span data-ttu-id="5fe15-108">Il *elenco di parametri* consiste in genere di nomi e, facoltativamente, tipi di parametri.</span><span class="sxs-lookup"><span data-stu-id="5fe15-108">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="5fe15-109">Più in generale, il *elenco di parametri* può essere composto da qualsiasi modello F #.</span><span class="sxs-lookup"><span data-stu-id="5fe15-109">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="5fe15-110">Per un elenco completo di modelli possibili, vedere [criteri di ricerca](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="5fe15-110">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="5fe15-111">Elenchi di parametri validi includono i seguenti esempi.</span><span class="sxs-lookup"><span data-stu-id="5fe15-111">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="5fe15-112">Il *espressione* è il corpo della funzione, di cui l'ultima espressione genera un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="5fe15-112">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="5fe15-113">Esempi di espressioni lambda validi includono:</span><span class="sxs-lookup"><span data-stu-id="5fe15-113">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="5fe15-114">Uso di espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="5fe15-114">Using Lambda Expressions</span></span>
<span data-ttu-id="5fe15-115">Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare il lavoro aggiuntivo della definizione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="5fe15-115">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="5fe15-116">Molte funzioni della libreria F # accettano valori di funzione come argomenti e può risultare particolarmente utile utilizzare un'espressione lambda in questi casi.</span><span class="sxs-lookup"><span data-stu-id="5fe15-116">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="5fe15-117">Il codice seguente si applica un'espressione lambda a elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="5fe15-117">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="5fe15-118">In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="5fe15-118">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="5fe15-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fe15-119">See Also</span></span>
[<span data-ttu-id="5fe15-120">Funzioni</span><span class="sxs-lookup"><span data-stu-id="5fe15-120">Functions</span></span>](index.md)
