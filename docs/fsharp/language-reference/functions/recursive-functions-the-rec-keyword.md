---
title: 'Funzioni ricorsive: parola chiave rec (F#)'
description: "Informazioni su come la parola chiave 'rec' di F # viene usata con la parola chiave 'let'. per definire una funzione ricorsiva."
ms.date: 05/16/2016
ms.openlocfilehash: 5aab6ed8ab0fc3c0f0bcfc93c3ce6518ec53254f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745971"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="85a01-103">Funzioni ricorsive: parola chiave rec</span><span class="sxs-lookup"><span data-stu-id="85a01-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="85a01-104">Il `rec` parola chiave viene usata in combinazione con il `let` parola chiave per definire una funzione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="85a01-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="85a01-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85a01-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="85a01-106">Note</span><span class="sxs-lookup"><span data-stu-id="85a01-106">Remarks</span></span>

<span data-ttu-id="85a01-107">Funzioni ricorsive, le funzioni che chiamano se stesse, vengono identificate in modo esplicito nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="85a01-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="85a01-108">Ciò rende disponibili l'identificatore che viene definito nell'ambito della funzione.</span><span class="sxs-lookup"><span data-stu-id="85a01-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="85a01-109">Il codice seguente illustra una funzione ricorsiva che calcola la *n*<sup>th</sup> numero di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="85a01-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="85a01-110">In pratica, codice come quello precedente è dispendioso di memoria e tempo processore dal momento che implica il ricalcolo di valori calcolati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="85a01-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="85a01-111">I metodi sono implicitamente ricorsivo all'interno del tipo; non è necessario aggiungere il `rec` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="85a01-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="85a01-112">Associazioni let nelle classi sono implicitamente non ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="85a01-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="85a01-113">Funzioni ricorsive reciproche</span><span class="sxs-lookup"><span data-stu-id="85a01-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="85a01-114">Le funzioni sono talvolta *ricorsive reciproche*, vale a dire le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con qualsiasi numero di chiamate tra.</span><span class="sxs-lookup"><span data-stu-id="85a01-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="85a01-115">È necessario definire tali funzioni tra loro in quello `let` binding, utilizzando il `and` parola chiave per collegarli tra loro.</span><span class="sxs-lookup"><span data-stu-id="85a01-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="85a01-116">Nell'esempio seguente vengono illustrati due si escludono a vicenda funzioni ricorsive.</span><span class="sxs-lookup"><span data-stu-id="85a01-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="85a01-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85a01-117">See also</span></span>

- [<span data-ttu-id="85a01-118">Funzioni</span><span class="sxs-lookup"><span data-stu-id="85a01-118">Functions</span></span>](index.md)
