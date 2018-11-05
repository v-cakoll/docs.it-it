---
title: 'Espressioni lambda: parola chiave fun (F#)'
description: Informazioni su come usare la parola chiave 'divertente' di F# per definire un'espressione lambda, che è una funzione anonima.
ms.date: 05/16/2016
ms.openlocfilehash: a37757f6b7328cd348bbf13f058a6dbc881769cf
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "47231021"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="d693e-103">Espressioni lambda: parola chiave fun (F#)</span><span class="sxs-lookup"><span data-stu-id="d693e-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="d693e-104">Il `fun` parola chiave viene usata per definire un'espressione lambda, vale a dire, una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="d693e-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="d693e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d693e-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="d693e-106">Note</span><span class="sxs-lookup"><span data-stu-id="d693e-106">Remarks</span></span>

<span data-ttu-id="d693e-107">Il *elenco di parametri* costituito in genere i nomi e, facoltativamente, i tipi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="d693e-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="d693e-108">Più in generale, il *elenco di parametri* può essere costituita da eventuali criteri F#.</span><span class="sxs-lookup"><span data-stu-id="d693e-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="d693e-109">Per un elenco completo delle possibili modelli, vedere [criteri di ricerca](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="d693e-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="d693e-110">Elenchi di parametri validi includono gli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d693e-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="d693e-111">Il *espressione* è il corpo della funzione, di cui l'ultima espressione genera un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="d693e-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="d693e-112">Esempi di espressioni lambda validi includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d693e-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="d693e-113">Uso di espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="d693e-113">Using Lambda Expressions</span></span>

<span data-ttu-id="d693e-114">Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni su un elenco o un'altra raccolta e si desidera evitare le attività aggiuntive di definizione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="d693e-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="d693e-115">Molte funzioni della libreria F# che accettano valori di funzione come argomenti e può essere particolarmente utile usare un'espressione lambda in questi casi.</span><span class="sxs-lookup"><span data-stu-id="d693e-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="d693e-116">Il codice seguente si applica un'espressione lambda a elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="d693e-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="d693e-117">In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="d693e-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="d693e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d693e-118">See also</span></span>

- [<span data-ttu-id="d693e-119">Funzioni</span><span class="sxs-lookup"><span data-stu-id="d693e-119">Functions</span></span>](index.md)
