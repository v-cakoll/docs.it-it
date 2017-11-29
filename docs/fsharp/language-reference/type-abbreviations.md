---
title: Abbreviazioni dei tipi (F#)
description: "Informazioni su F # le abbreviazioni di tipo per assegnare un nome più significativo di un tipo per rendere il codice più facile da leggere."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 560af74f-935f-415c-af56-604cddb9da6b
ms.openlocfilehash: 235c0240fe89d203b9474dec2b3f91947f453cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-abbreviations"></a><span data-ttu-id="44cd8-104">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="44cd8-104">Type Abbreviations</span></span>

<span data-ttu-id="44cd8-105">Oggetto *abbreviazione di tipo* è un alias o nome alternativo per un tipo.</span><span class="sxs-lookup"><span data-stu-id="44cd8-105">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="44cd8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44cd8-106">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="44cd8-107">Note</span><span class="sxs-lookup"><span data-stu-id="44cd8-107">Remarks</span></span>
<span data-ttu-id="44cd8-108">È possibile utilizzare le abbreviazioni di tipo per assegnare un tipo di un nome più significativo, per rendere il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="44cd8-108">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="44cd8-109">È possibile utilizzare tali per creare un nome facile da usare per un tipo che è altrimenti difficili da scrivere. Inoltre, è possibile utilizzare le abbreviazioni di tipo per renderne più semplice modificare un tipo sottostante senza modificare tutto il codice che utilizza il tipo.</span><span class="sxs-lookup"><span data-stu-id="44cd8-109">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="44cd8-110">Di seguito è un'abbreviazione di tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="44cd8-110">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="44cd8-111">Abbreviazioni dei tipi possono includere parametri generici, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="44cd8-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="44cd8-112">Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un singolo argomento di qualsiasi tipo e restituisce un singolo valore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="44cd8-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="44cd8-113">Le abbreviazioni di tipo non vengono mantenute nel codice MSIL di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44cd8-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="44cd8-114">Pertanto, quando si utilizza un assembly F # da un altro linguaggio .NET Framework, è necessario utilizzare il nome del tipo sottostante di un'abbreviazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="44cd8-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="44cd8-115">Le abbreviazioni di tipo consente inoltre alle unità di misura.</span><span class="sxs-lookup"><span data-stu-id="44cd8-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="44cd8-116">Per ulteriori informazioni, vedere [unità di misura](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="44cd8-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="44cd8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44cd8-117">See Also</span></span>
[<span data-ttu-id="44cd8-118">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="44cd8-118">F# Language Reference</span></span>](index.md)

