---
title: 'Espressione Loops: for...to'
description: Vedere il F# for... su espressione viene usato per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.
ms.date: 05/16/2016
ms.openlocfilehash: 041e98fa4bcc140aa3cd699f6ed35bf52c8b4175
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904033"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="037f1-103">Espressione Loops: for...to</span><span class="sxs-lookup"><span data-stu-id="037f1-103">Loops: for...to Expression</span></span>

<span data-ttu-id="037f1-104">Il `for...to` espressione viene usata per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.</span><span class="sxs-lookup"><span data-stu-id="037f1-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="037f1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="037f1-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="037f1-106">Note</span><span class="sxs-lookup"><span data-stu-id="037f1-106">Remarks</span></span>

<span data-ttu-id="037f1-107">Il tipo dell'identificatore viene dedotto dal tipo dei *avviare* e *fine* espressioni.</span><span class="sxs-lookup"><span data-stu-id="037f1-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="037f1-108">I tipi per queste espressioni devono essere numeri interi a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="037f1-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="037f1-109">Anche se tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativa.</span><span class="sxs-lookup"><span data-stu-id="037f1-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="037f1-110">Il tipo restituito per il *corpo-expression* deve essere `unit`.</span><span class="sxs-lookup"><span data-stu-id="037f1-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="037f1-111">Gli esempi seguenti illustrano vari usi del `for...to` espressione.</span><span class="sxs-lookup"><span data-stu-id="037f1-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="037f1-112">Di seguito è riportato l'output del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="037f1-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="037f1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="037f1-113">See also</span></span>

- [<span data-ttu-id="037f1-114">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="037f1-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="037f1-115">Cicli: `for...in` Expression</span><span class="sxs-lookup"><span data-stu-id="037f1-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="037f1-116">Cicli: `while...do` Expression</span><span class="sxs-lookup"><span data-stu-id="037f1-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)