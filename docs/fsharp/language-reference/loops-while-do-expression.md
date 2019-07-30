---
title: 'Espressione Loops: while...do'
description: Scopri come... l'espressione do viene utilizzata per eseguire l'esecuzione iterativa (ciclo) mentre una condizione di test specificata è true.
ms.date: 05/16/2016
ms.openlocfilehash: f05bdd9f8f4b9446d59f68e1231fb75e18e9b526
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630763"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="93b90-103">Espressione Loops: while...do</span><span class="sxs-lookup"><span data-stu-id="93b90-103">Loops: while...do Expression</span></span>

<span data-ttu-id="93b90-104">L' `while...do` espressione viene utilizzata per eseguire l'esecuzione iterativa (ciclo), mentre una condizione di test specificata è true.</span><span class="sxs-lookup"><span data-stu-id="93b90-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="93b90-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93b90-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="93b90-106">Note</span><span class="sxs-lookup"><span data-stu-id="93b90-106">Remarks</span></span>

<span data-ttu-id="93b90-107">*Test-Expression* viene valutato. in caso contrario ,l'espressioneBodyvieneeseguitael'espressioneditestvienenuovamentevalutata`true`.</span><span class="sxs-lookup"><span data-stu-id="93b90-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="93b90-108">*Body-Expression* deve essere di tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="93b90-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="93b90-109">Se l'espressione di test `false`è, termina l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="93b90-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="93b90-110">Nell'esempio seguente viene illustrato l'utilizzo dell' `while...do` espressione.</span><span class="sxs-lookup"><span data-stu-id="93b90-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="93b90-111">L'output del codice precedente è un flusso di numeri casuali compresi tra 1 e 20, l'ultimo dei quali è 10.</span><span class="sxs-lookup"><span data-stu-id="93b90-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="93b90-112">È possibile utilizzare `while...do` nelle espressioni di sequenza e in altre espressioni `while...do` di calcolo, nel qual caso viene utilizzata una versione personalizzata dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="93b90-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="93b90-113">Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di calcolo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="93b90-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93b90-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93b90-114">See also</span></span>

- [<span data-ttu-id="93b90-115">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="93b90-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="93b90-116">Cicli `for...in`Espressione</span><span class="sxs-lookup"><span data-stu-id="93b90-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="93b90-117">Cicli `for...to`Espressione</span><span class="sxs-lookup"><span data-stu-id="93b90-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
