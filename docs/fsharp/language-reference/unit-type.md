---
title: Tipo di unità (F#)
description: "Informazioni su come il tipo 'unit' F # viene spesso utilizzato per indicare la posizione in cui è necessario un valore per la sintassi del linguaggio quando nessun valore è necessario o desiderato."
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097152"
---
# <a name="unit-type"></a><span data-ttu-id="1479d-103">Tipo di unità</span><span class="sxs-lookup"><span data-stu-id="1479d-103">Unit Type</span></span>

<span data-ttu-id="1479d-104">Il `unit` tipo è un tipo che indica l'assenza di un valore specifico; il `unit` tipo ha un solo valore, che funge da segnaposto quando nessun altro valore è presente o necessario.</span><span class="sxs-lookup"><span data-stu-id="1479d-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="1479d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1479d-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="1479d-106">Note</span><span class="sxs-lookup"><span data-stu-id="1479d-106">Remarks</span></span>

<span data-ttu-id="1479d-107">Tutte le espressioni F # devono restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="1479d-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="1479d-108">Per le espressioni che non generano un valore che è di particolare interesse, il valore di tipo `unit` viene usato.</span><span class="sxs-lookup"><span data-stu-id="1479d-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="1479d-109">Il `unit` è simile a tipo di `void` tipo nei linguaggi come c# e C++.</span><span class="sxs-lookup"><span data-stu-id="1479d-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="1479d-110">Il `unit` tipo ha un singolo valore e tale valore è indicato dal token `()`.</span><span class="sxs-lookup"><span data-stu-id="1479d-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="1479d-111">Il valore della `unit` tipo viene spesso usato in F # programming per indicare la posizione in cui è richiesto un valore dalla sintassi del linguaggio, ma quando nessun valore è necessario o desiderato.</span><span class="sxs-lookup"><span data-stu-id="1479d-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="1479d-112">Un esempio potrebbe essere il valore restituito di un `printf` (funzione).</span><span class="sxs-lookup"><span data-stu-id="1479d-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="1479d-113">Poiché le azioni di importanti il `printf` eseguire operazioni nella funzione, la funzione non deve restituire un valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="1479d-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="1479d-114">Pertanto, il valore restituito è di tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="1479d-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="1479d-115">Alcuni costrutti prevedono un `unit` valore.</span><span class="sxs-lookup"><span data-stu-id="1479d-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="1479d-116">Ad esempio, un `do` binding o qualsiasi codice al livello superiore di un modulo è previsto in modo che restituisca un `unit` valore.</span><span class="sxs-lookup"><span data-stu-id="1479d-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="1479d-117">Il compilatore genera un avviso quando un `do` al codice al livello superiore di un modulo o associazione produce un risultato diverso dal `unit` valore non usato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1479d-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="1479d-118">Questo avviso è una caratteristica della programmazione funzionale; non fa in altri linguaggi di programmazione .NET.</span><span class="sxs-lookup"><span data-stu-id="1479d-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="1479d-119">In un programma puramente funzionale, in cui le funzioni ha effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="1479d-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="1479d-120">Pertanto, quando il risultato viene ignorato, è un possibile errore di programmazione.</span><span class="sxs-lookup"><span data-stu-id="1479d-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="1479d-121">Sebbene F # non sia un linguaggio di programmazione puramente funzionale, è buona norma da seguire dello stile di programmazione funzionale, laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="1479d-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="1479d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1479d-122">See also</span></span>

- [<span data-ttu-id="1479d-123">Primitivi</span><span class="sxs-lookup"><span data-stu-id="1479d-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="1479d-124">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1479d-124">F# Language Reference</span></span>](index.md)
