---
title: 'Funzioni ricorsive: parola chiave rec (F#)'
description: 'Informazioni su come la parola chiave ''rec'' F # viene utilizzata con la parola chiave ''let'' per definire una funzione ricorsiva.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="20af5-104">Funzioni ricorsive: parola chiave rec</span><span class="sxs-lookup"><span data-stu-id="20af5-104">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="20af5-105">Il `rec` parola chiave viene utilizzata in combinazione con il `let` (parola chiave) per definire una funzione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="20af5-105">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="20af5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20af5-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="20af5-107">Note</span><span class="sxs-lookup"><span data-stu-id="20af5-107">Remarks</span></span>
<span data-ttu-id="20af5-108">Funzioni ricorsive, le funzioni che chiamano se stesse, vengono identificate in modo esplicito nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="20af5-108">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="20af5-109">Ciò rende disponibile l'identificatore che viene definito nell'ambito della funzione.</span><span class="sxs-lookup"><span data-stu-id="20af5-109">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="20af5-110">Il codice seguente viene illustrata una funzione ricorsiva che calcola il  *n* numero di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="20af5-110">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="20af5-111">In pratica, codice come quello precedente è causano un elevato utilizzo di memoria e tempo processore perché prevede la il ricalcolo di valori calcolati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="20af5-111">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="20af5-112">I metodi sono implicitamente ricorsiva all'interno del tipo; non è necessario aggiungere il `rec` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="20af5-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="20af5-113">Associazioni let nelle classi non sono implicitamente ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="20af5-113">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="20af5-114">Funzioni ricorsive reciproche</span><span class="sxs-lookup"><span data-stu-id="20af5-114">Mutually Recursive Functions</span></span>
<span data-ttu-id="20af5-115">Talvolta le funzioni sono *ricorsive reciproche*, ovvero le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con un numero qualsiasi di chiamate tra.</span><span class="sxs-lookup"><span data-stu-id="20af5-115">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="20af5-116">È necessario definire tali funzioni in quella `let` binding, utilizzando il `and` (parola chiave) per collegarle.</span><span class="sxs-lookup"><span data-stu-id="20af5-116">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="20af5-117">Nell'esempio seguente vengono illustrati due reciprocamente funzioni ricorsive.</span><span class="sxs-lookup"><span data-stu-id="20af5-117">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="20af5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20af5-118">See Also</span></span>
[<span data-ttu-id="20af5-119">Funzioni</span><span class="sxs-lookup"><span data-stu-id="20af5-119">Functions</span></span>](index.md)
