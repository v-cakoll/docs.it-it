---
title: 'Funzioni ricorsive: Parola chiave REC'
description: Viene illustrato come F# usare la parola chiave ' REC ' con la parola chiave ' Let ' per definire una funzione ricorsiva.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630648"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="1307e-103">Funzioni ricorsive: Parola chiave REC</span><span class="sxs-lookup"><span data-stu-id="1307e-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="1307e-104">La `rec` parola chiave viene utilizzata insieme `let` alla parola chiave per definire una funzione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="1307e-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="1307e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1307e-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="1307e-106">Note</span><span class="sxs-lookup"><span data-stu-id="1307e-106">Remarks</span></span>

<span data-ttu-id="1307e-107">Le F# funzioni ricorsive, funzioni che chiamano se stesse, vengono identificate in modo esplicito nel linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1307e-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="1307e-108">In questo modo, identificatore viene definito disponibile nell'ambito della funzione.</span><span class="sxs-lookup"><span data-stu-id="1307e-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="1307e-109">Il codice seguente illustra una funzione ricorsiva che calcola il numero di<sup>Fibonacci</sup> n.</span><span class="sxs-lookup"><span data-stu-id="1307e-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="1307e-110">In pratica, il codice simile a quello precedente è uno spreco di memoria e tempo del processore perché comporta il ricalcolo dei valori calcolati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1307e-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="1307e-111">I metodi sono implicitamente ricorsivi all'interno del tipo. non è necessario aggiungere la `rec` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="1307e-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="1307e-112">Le associazioni let all'interno delle classi non sono implicitamente ricorsive.</span><span class="sxs-lookup"><span data-stu-id="1307e-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="1307e-113">Funzioni ricorsive reciproche</span><span class="sxs-lookup"><span data-stu-id="1307e-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="1307e-114">A volte lefunzioni sono reciprocamente ricorsive, vale a dire che le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con un numero qualsiasi di chiamate tra.</span><span class="sxs-lookup"><span data-stu-id="1307e-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="1307e-115">È necessario definire tali funzioni insieme nell'associazione uno `let` , usando la `and` parola chiave per collegarle insieme.</span><span class="sxs-lookup"><span data-stu-id="1307e-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="1307e-116">Nell'esempio seguente vengono illustrate due funzioni ricorsive reciproche.</span><span class="sxs-lookup"><span data-stu-id="1307e-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="1307e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1307e-117">See also</span></span>

- [<span data-ttu-id="1307e-118">Funzioni</span><span class="sxs-lookup"><span data-stu-id="1307e-118">Functions</span></span>](index.md)
