---
title: Abbreviazioni dei tipi (F#)
description: 'Informazioni su F # le abbreviazioni dei tipi per assegnare un nome più significativo di un tipo per rendere il codice più facile da leggere.'
ms.date: 05/16/2016
ms.openlocfilehash: 259cd6c84e22fc7c98e08255d3e0ded5b87af352
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481543"
---
# <a name="type-abbreviations"></a><span data-ttu-id="9afa4-103">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="9afa4-103">Type Abbreviations</span></span>

<span data-ttu-id="9afa4-104">Oggetto *abbreviazione di tipo* è un alias o nome alternativo per un tipo.</span><span class="sxs-lookup"><span data-stu-id="9afa4-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="9afa4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9afa4-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="9afa4-106">Note</span><span class="sxs-lookup"><span data-stu-id="9afa4-106">Remarks</span></span>

<span data-ttu-id="9afa4-107">È possibile utilizzare le abbreviazioni dei tipi per assegnare un tipo di un nome più significativo, per rendere il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="9afa4-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="9afa4-108">È anche possibile utilizzarli per creare un nome facile da usare per un tipo che è altrimenti difficile da scrivere. Inoltre, è possibile utilizzare le abbreviazioni dei tipi per renderne più semplice modificare un tipo sottostante senza dover modificare tutto il codice che usa il tipo.</span><span class="sxs-lookup"><span data-stu-id="9afa4-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="9afa4-109">Di seguito è un'abbreviazione di tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="9afa4-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="9afa4-110">Per impostazione predefinita l'accessibilità delle abbreviazioni di tipo `public`.</span><span class="sxs-lookup"><span data-stu-id="9afa4-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="9afa4-111">Abbreviazioni dei tipi possono includere i parametri generici, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9afa4-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="9afa4-112">Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un singolo argomento di qualsiasi tipo e che restituisce un singolo valore di quel tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="9afa4-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="9afa4-113">Abbreviazioni dei tipi non vengono mantenute nel codice .NET Framework MSIL.</span><span class="sxs-lookup"><span data-stu-id="9afa4-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="9afa4-114">Pertanto, quando si usa un assembly F # da un altro linguaggio .NET Framework, è necessario utilizzare il nome del tipo sottostante per un tipo unitnames.</span><span class="sxs-lookup"><span data-stu-id="9afa4-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="9afa4-115">Abbreviazioni dei tipi sono utilizzabili anche in unità di misura.</span><span class="sxs-lookup"><span data-stu-id="9afa4-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="9afa4-116">Per altre informazioni, vedere [unità di misura](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="9afa4-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9afa4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9afa4-117">See also</span></span>

- [<span data-ttu-id="9afa4-118">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="9afa4-118">F# Language Reference</span></span>](index.md)
