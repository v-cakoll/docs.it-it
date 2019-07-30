---
title: Tipo di unità
description: Informazioni sul modo F# in cui il tipo di "unità" viene spesso usato per mantenere la posizione in cui un valore è richiesto dalla sintassi del linguaggio quando non è necessario o si desidera alcun valore.
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630169"
---
# <a name="unit-type"></a><span data-ttu-id="f82ce-103">Tipo di unità</span><span class="sxs-lookup"><span data-stu-id="f82ce-103">Unit Type</span></span>

<span data-ttu-id="f82ce-104">Il `unit` tipo è un tipo che indica l'assenza di un valore specifico. il `unit` tipo dispone solo di un singolo valore, che funge da segnaposto quando non esiste alcun altro valore o è necessario.</span><span class="sxs-lookup"><span data-stu-id="f82ce-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f82ce-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f82ce-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="f82ce-106">Note</span><span class="sxs-lookup"><span data-stu-id="f82ce-106">Remarks</span></span>

<span data-ttu-id="f82ce-107">Ogni F# espressione deve restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="f82ce-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="f82ce-108">Per le espressioni che non generano un valore di interesse, viene usato il valore di `unit` tipo.</span><span class="sxs-lookup"><span data-stu-id="f82ce-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="f82ce-109">Il `unit` tipo è simile al `void` tipo in linguaggi quali C# e C++.</span><span class="sxs-lookup"><span data-stu-id="f82ce-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="f82ce-110">Il `unit` tipo ha un solo valore e tale valore è indicato dal token `()`.</span><span class="sxs-lookup"><span data-stu-id="f82ce-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="f82ce-111">Il valore del `unit` tipo viene spesso utilizzato nella programmazione F# per conservare la posizione in cui è richiesto un valore per la sintassi del linguaggio, ma quando non è necessario o desiderato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="f82ce-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="f82ce-112">Un esempio potrebbe essere il valore restituito di una `printf` funzione.</span><span class="sxs-lookup"><span data-stu-id="f82ce-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="f82ce-113">Poiché le azioni importanti dell' `printf` operazione si verificano nella funzione, non è necessario che la funzione restituisca un valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="f82ce-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="f82ce-114">Pertanto, il valore restituito è di tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="f82ce-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="f82ce-115">Alcuni costrutti prevedono un `unit` valore.</span><span class="sxs-lookup"><span data-stu-id="f82ce-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="f82ce-116">Ad esempio, è `do` previsto che un binding o qualsiasi codice al primo livello di un modulo restituisca un `unit` valore.</span><span class="sxs-lookup"><span data-stu-id="f82ce-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="f82ce-117">Il compilatore segnala un avviso quando un' `do` associazione o un codice al livello superiore di un modulo produce un risultato diverso dal `unit` valore non usato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f82ce-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="f82ce-118">Questo avviso è una caratteristica della programmazione funzionale. non viene visualizzato in altri linguaggi di programmazione .NET.</span><span class="sxs-lookup"><span data-stu-id="f82ce-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="f82ce-119">In un programma puramente funzionale, in cui le funzioni non hanno effetti collaterali, il valore restituito finale è l'unico risultato di una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="f82ce-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="f82ce-120">Pertanto, quando il risultato viene ignorato, è possibile che si verifichi un errore di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f82ce-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="f82ce-121">Sebbene F# non sia un linguaggio di programmazione puramente funzionale, è consigliabile seguire lo stile di programmazione funzionale laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="f82ce-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="f82ce-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f82ce-122">See also</span></span>

- [<span data-ttu-id="f82ce-123">Primitivi</span><span class="sxs-lookup"><span data-stu-id="f82ce-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="f82ce-124">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f82ce-124">F# Language Reference</span></span>](index.md)
