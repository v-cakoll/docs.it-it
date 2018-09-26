---
title: Tipi flessibili (F#)
description: 'Informazioni su come utilizzare F # annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore è un tipo compatibile con un tipo specificato.'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47210045"
---
# <a name="flexible-types"></a><span data-ttu-id="d2279-103">Tipi flessibili</span><span class="sxs-lookup"><span data-stu-id="d2279-103">Flexible Types</span></span>

<span data-ttu-id="d2279-104">Oggetto *annotazione di tipo flessibile* indica che un parametro, una variabile o un valore ha un tipo compatibile con il tipo specificato, in cui compatibilità viene determinata dalla posizione in una gerarchia orientata agli oggetti di classi o interfacce.</span><span class="sxs-lookup"><span data-stu-id="d2279-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="d2279-105">Tipi flessibili sono utili soprattutto quando non si verifica la conversione automatica a tipi di livello superiori nella gerarchia dei tipi, ma si desidera abilitare la funzionalità lavorare con qualsiasi tipo nella gerarchia o qualsiasi tipo che implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d2279-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2279-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2279-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="d2279-107">Note</span><span class="sxs-lookup"><span data-stu-id="d2279-107">Remarks</span></span>

<span data-ttu-id="d2279-108">Nella sintassi precedente *tipo* rappresenta un'interfaccia o un tipo di base.</span><span class="sxs-lookup"><span data-stu-id="d2279-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="d2279-109">Un tipo flessibile è equivalente a un tipo generico che ha un vincolo che limita i tipi consentiti in tipi compatibili con il tipo di base o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d2279-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="d2279-110">Vale a dire, le due righe di codice seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d2279-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="d2279-111">Tipi flessibili sono utili in diversi tipi di situazioni.</span><span class="sxs-lookup"><span data-stu-id="d2279-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="d2279-112">Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), è spesso utile avere la funzione restituisce un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="d2279-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="d2279-113">Nell'esempio seguente, l'uso di un tipo flessibile con un argomento di sequenza in `iterate2` consente alla funzione di ordine superiore lavorare con le funzioni che generano le sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="d2279-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="d2279-114">Prendere in considerazione le seguenti due funzioni, uno dei quali restituisce una sequenza, l'altro restituisce un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="d2279-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="d2279-115">Come ulteriore esempio, prendere in considerazione la [Seq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) funzione della libreria:</span><span class="sxs-lookup"><span data-stu-id="d2279-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="d2279-116">È possibile passare una delle seguenti sequenze enumerabili a questa funzione:</span><span class="sxs-lookup"><span data-stu-id="d2279-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="d2279-117">Un elenco di elenchi</span><span class="sxs-lookup"><span data-stu-id="d2279-117">A list of lists</span></span>
- <span data-ttu-id="d2279-118">Un elenco di matrici</span><span class="sxs-lookup"><span data-stu-id="d2279-118">A list of arrays</span></span>
- <span data-ttu-id="d2279-119">Una matrice di elenchi</span><span class="sxs-lookup"><span data-stu-id="d2279-119">An array of lists</span></span>
- <span data-ttu-id="d2279-120">Matrice di sequenze</span><span class="sxs-lookup"><span data-stu-id="d2279-120">An array of sequences</span></span>
- <span data-ttu-id="d2279-121">Qualsiasi altra combinazione di sequenze enumerabili</span><span class="sxs-lookup"><span data-stu-id="d2279-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="d2279-122">Il codice seguente usa `Seq.concat` per illustrare gli scenari che è possibile supportare usando tipi flessibili.</span><span class="sxs-lookup"><span data-stu-id="d2279-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="d2279-123">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d2279-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="d2279-124">In F #, come in altri linguaggi orientati, vi sono contesti in cui i tipi che implementano interfacce o tipi derivati vengono convertiti automaticamente a un tipo di interfaccia o un tipo di base.</span><span class="sxs-lookup"><span data-stu-id="d2279-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="d2279-125">Negli argomenti diretti, ma non quando il tipo è in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione o come argomento di tipo, si verificano queste conversioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="d2279-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="d2279-126">Di conseguenza, la notazione di tipo flessibile risulta particolarmente utile quando il tipo a che si applica fa parte di un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="d2279-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2279-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2279-127">See also</span></span>

- [<span data-ttu-id="d2279-128">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="d2279-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d2279-129">Generics</span><span class="sxs-lookup"><span data-stu-id="d2279-129">Generics</span></span>](generics/index.md)
