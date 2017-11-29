---
title: 'Cicli: espressioni while...do (F#)'
description: "Vedere come while... tale espressione viene utilizzata per l'esecuzione iterativa (ciclo) quando una condizione di test specificato è true."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 6a186d75dcda383764949c2cd3b09bc9e3d1080a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="91a54-104">Espressione Loops: while...do</span><span class="sxs-lookup"><span data-stu-id="91a54-104">Loops: while...do Expression</span></span>

<span data-ttu-id="91a54-105">Il `while...do` espressione viene utilizzata per l'esecuzione iterativa (ciclo) quando una condizione di test specificato è true.</span><span class="sxs-lookup"><span data-stu-id="91a54-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="91a54-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91a54-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="91a54-107">Note</span><span class="sxs-lookup"><span data-stu-id="91a54-107">Remarks</span></span>
<span data-ttu-id="91a54-108">Il *espressione di test* viene valutato; se è `true`, *espressione corpo* viene eseguita e l'espressione di test viene valutata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="91a54-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="91a54-109">Il *espressione corpo* deve avere tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="91a54-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="91a54-110">Se l'espressione di test è `false`, termina l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="91a54-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="91a54-111">Nell'esempio seguente viene illustrato l'utilizzo del `while...do` espressione.</span><span class="sxs-lookup"><span data-stu-id="91a54-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="91a54-112">L'output del codice precedente è un flusso di numeri casuali compresi tra 1 e 20, di cui l'ultimo è 10.</span><span class="sxs-lookup"><span data-stu-id="91a54-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="91a54-113">È possibile utilizzare `while...do` in espressioni sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `while...do` viene utilizzata l'espressione.</span><span class="sxs-lookup"><span data-stu-id="91a54-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="91a54-114">Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="91a54-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="91a54-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91a54-115">See Also</span></span>
[<span data-ttu-id="91a54-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="91a54-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="91a54-117">Cicli: espressione `for...in`</span><span class="sxs-lookup"><span data-stu-id="91a54-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="91a54-118">Cicli: espressione `for...to`</span><span class="sxs-lookup"><span data-stu-id="91a54-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
