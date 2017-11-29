---
title: 'Cicli: espressione for...to (F#)'
description: 'Vedere come il ciclo for di F #... per l''espressione viene utilizzato per eseguire l''iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="25eef-104">Espressione Loops: for...to</span><span class="sxs-lookup"><span data-stu-id="25eef-104">Loops: for...to Expression</span></span>

<span data-ttu-id="25eef-105">Il `for...to` espressione viene utilizzata per eseguire l'iterazione in un ciclo su un intervallo di valori di una variabile di ciclo.</span><span class="sxs-lookup"><span data-stu-id="25eef-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="25eef-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25eef-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="25eef-107">Note</span><span class="sxs-lookup"><span data-stu-id="25eef-107">Remarks</span></span>
<span data-ttu-id="25eef-108">Il tipo dell'identificatore viene dedotto dal tipo del *avviare* e *fine* espressioni.</span><span class="sxs-lookup"><span data-stu-id="25eef-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="25eef-109">Tipi per le espressioni devono essere numeri interi a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="25eef-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="25eef-110">Anche se tecnicamente un'espressione, `for...to` è più simile a un'istruzione tradizionale in un linguaggio di programmazione imperativa.</span><span class="sxs-lookup"><span data-stu-id="25eef-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="25eef-111">Il tipo restituito per il *espressione corpo* deve essere `unit`.</span><span class="sxs-lookup"><span data-stu-id="25eef-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="25eef-112">Gli esempi seguenti illustrano vari usi del `for...to` espressione.</span><span class="sxs-lookup"><span data-stu-id="25eef-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="25eef-113">Di seguito è riportato l'output del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="25eef-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="25eef-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25eef-114">See Also</span></span>
[<span data-ttu-id="25eef-115">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="25eef-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="25eef-116">Cicli: espressione `for...in`</span><span class="sxs-lookup"><span data-stu-id="25eef-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="25eef-117">Cicli: espressione `while...do`</span><span class="sxs-lookup"><span data-stu-id="25eef-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
