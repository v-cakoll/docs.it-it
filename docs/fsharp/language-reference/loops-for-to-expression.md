---
title: 'Espressione Loops: for...to'
description: Vedere come il F# ... l'espressione to viene utilizzata per eseguire un'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283911"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="d8b9e-103">Espressione Loops: for...to</span><span class="sxs-lookup"><span data-stu-id="d8b9e-103">Loops: for...to Expression</span></span>

<span data-ttu-id="d8b9e-104">L'espressione `for...to` viene utilizzata per eseguire un'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8b9e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8b9e-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="d8b9e-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8b9e-106">Remarks</span></span>

<span data-ttu-id="d8b9e-107">Il tipo dell'identificatore viene dedotto dal tipo delle espressioni di *inizio* e *fine* .</span><span class="sxs-lookup"><span data-stu-id="d8b9e-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="d8b9e-108">I tipi per queste espressioni devono essere interi a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="d8b9e-109">Sebbene tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativo.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="d8b9e-110">Il tipo restituito per *Body-Expression* deve essere `unit`.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="d8b9e-111">Negli esempi seguenti vengono illustrati diversi utilizzi dell'espressione `for...to`.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="d8b9e-112">Di seguito è riportato l'output del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="d8b9e-112">The output of the previous code is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="d8b9e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b9e-113">See also</span></span>

- [<span data-ttu-id="d8b9e-114">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="d8b9e-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d8b9e-115">Cicli: espressione `for...in`</span><span class="sxs-lookup"><span data-stu-id="d8b9e-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="d8b9e-116">Cicli: espressione `while...do`</span><span class="sxs-lookup"><span data-stu-id="d8b9e-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
