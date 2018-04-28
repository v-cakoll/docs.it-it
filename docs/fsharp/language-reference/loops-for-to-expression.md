---
title: 'Cicli: espressione for...to (F#)'
description: "Vedere come il ciclo for di F #... per l'espressione viene utilizzato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a><span data-ttu-id="b92ec-103">Espressione Loops: for...to</span><span class="sxs-lookup"><span data-stu-id="b92ec-103">Loops: for...to Expression</span></span>

<span data-ttu-id="b92ec-104">Il `for...to` espressione viene utilizzata per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.</span><span class="sxs-lookup"><span data-stu-id="b92ec-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="b92ec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b92ec-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="b92ec-106">Note</span><span class="sxs-lookup"><span data-stu-id="b92ec-106">Remarks</span></span>
<span data-ttu-id="b92ec-107">Il tipo dell'identificatore viene dedotto dal tipo del *avviare* e *fine* espressioni.</span><span class="sxs-lookup"><span data-stu-id="b92ec-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="b92ec-108">Tipi per le espressioni devono essere numeri interi a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b92ec-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="b92ec-109">Anche se tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativa.</span><span class="sxs-lookup"><span data-stu-id="b92ec-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="b92ec-110">Il tipo restituito per il *espressione corpo* deve essere `unit`.</span><span class="sxs-lookup"><span data-stu-id="b92ec-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="b92ec-111">Gli esempi seguenti illustrano vari usi del `for...to` espressione.</span><span class="sxs-lookup"><span data-stu-id="b92ec-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="b92ec-112">Di seguito è riportato l'output del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="b92ec-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="b92ec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b92ec-113">See Also</span></span>
[<span data-ttu-id="b92ec-114">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="b92ec-114">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b92ec-115">Cicli: espressione `for...in`</span><span class="sxs-lookup"><span data-stu-id="b92ec-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="b92ec-116">Cicli: espressione `while...do`</span><span class="sxs-lookup"><span data-stu-id="b92ec-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
