---
title: Abbreviazioni dei tipi (F#)
description: 'Informazioni su F # le abbreviazioni di tipo per assegnare un nome più significativo di un tipo per rendere il codice più facile da leggere.'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058955"
---
# <a name="type-abbreviations"></a><span data-ttu-id="609f8-103">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="609f8-103">Type Abbreviations</span></span>

<span data-ttu-id="609f8-104">Oggetto *abbreviazione di tipo* è un alias o nome alternativo per un tipo.</span><span class="sxs-lookup"><span data-stu-id="609f8-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="609f8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="609f8-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="609f8-106">Note</span><span class="sxs-lookup"><span data-stu-id="609f8-106">Remarks</span></span>
<span data-ttu-id="609f8-107">È possibile utilizzare le abbreviazioni di tipo per assegnare un tipo di un nome più significativo, per rendere il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="609f8-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="609f8-108">È possibile utilizzare tali per creare un nome facile da usare per un tipo che è altrimenti difficili da scrivere. Inoltre, è possibile utilizzare le abbreviazioni di tipo per renderne più semplice modificare un tipo sottostante senza modificare tutto il codice che utilizza il tipo.</span><span class="sxs-lookup"><span data-stu-id="609f8-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="609f8-109">Di seguito è un'abbreviazione di tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="609f8-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="609f8-110">Per impostazione predefinita accessibilità di abbreviazioni dei tipi `public`.</span><span class="sxs-lookup"><span data-stu-id="609f8-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="609f8-111">Abbreviazioni dei tipi possono includere parametri generici, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="609f8-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="609f8-112">Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un singolo argomento di qualsiasi tipo e restituisce un singolo valore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="609f8-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="609f8-113">Le abbreviazioni di tipo non vengono mantenute nel codice MSIL di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="609f8-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="609f8-114">Pertanto, quando si utilizza un assembly F # da un altro linguaggio .NET Framework, è necessario utilizzare il nome del tipo sottostante di un'abbreviazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="609f8-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="609f8-115">Le abbreviazioni di tipo consente inoltre alle unità di misura.</span><span class="sxs-lookup"><span data-stu-id="609f8-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="609f8-116">Per ulteriori informazioni, vedere [unità di misura](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="609f8-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="609f8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="609f8-117">See Also</span></span>
[<span data-ttu-id="609f8-118">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="609f8-118">F# Language Reference</span></span>](index.md)

