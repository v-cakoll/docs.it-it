---
title: Tipi flessibili (F#)
description: "Informazioni sull'utilizzo di F # annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore è un tipo compatibile con un tipo specificato."
ms.date: 05/16/2016
ms.openlocfilehash: a54d462d04e4e65680a4612f58da72173f04d1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563350"
---
# <a name="flexible-types"></a><span data-ttu-id="ae3ad-103">Tipi flessibili</span><span class="sxs-lookup"><span data-stu-id="ae3ad-103">Flexible Types</span></span>

<span data-ttu-id="ae3ad-104">Oggetto *annotazione di tipo flessibile* indica che un parametro, una variabile o un valore è un tipo che è compatibile con un tipo specificato, in cui viene determinata la compatibilità in base alla posizione in una gerarchia orientata agli oggetti di classi o interfacce.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="ae3ad-105">Tipi flessibili sono utili in particolare quando non si verifica la conversione automatica per i tipi di livello superiori nella gerarchia dei tipi, ma si desidera abilitare l'utilizzo con qualsiasi tipo nella gerarchia o qualsiasi tipo che implementa un'interfaccia della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae3ad-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae3ad-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="ae3ad-107">Note</span><span class="sxs-lookup"><span data-stu-id="ae3ad-107">Remarks</span></span>

<span data-ttu-id="ae3ad-108">Nella sintassi precedente, *tipo* rappresenta un'interfaccia o un tipo di base.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="ae3ad-109">Un tipo flessibile è equivalente a un tipo generico che ha un vincolo che limita i tipi consentiti in tipi compatibili con il tipo di base o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="ae3ad-110">Vale a dire le due righe di codice seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="ae3ad-111">Tipi flessibili sono utili in situazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="ae3ad-112">Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), è spesso utile avere la funzione restituisca un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="ae3ad-113">Nell'esempio seguente, l'utilizzo di un tipo flessibile con un argomento di sequenza in `iterate2` consente alla funzione di ordine superiore lavorare con le funzioni che generano le sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="ae3ad-114">Prendere in considerazione le seguenti due funzioni, uno di cui viene restituita una sequenza, l'altro che restituisce un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="ae3ad-115">Un altro esempio, considerare il [SEQ](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) funzione della libreria:</span><span class="sxs-lookup"><span data-stu-id="ae3ad-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="ae3ad-116">È possibile passare una delle seguenti sequenze di enumerabile a questa funzione:</span><span class="sxs-lookup"><span data-stu-id="ae3ad-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="ae3ad-117">Un elenco di elenchi</span><span class="sxs-lookup"><span data-stu-id="ae3ad-117">A list of lists</span></span>
- <span data-ttu-id="ae3ad-118">Un elenco di matrici</span><span class="sxs-lookup"><span data-stu-id="ae3ad-118">A list of arrays</span></span>
- <span data-ttu-id="ae3ad-119">Matrice di elenchi</span><span class="sxs-lookup"><span data-stu-id="ae3ad-119">An array of lists</span></span>
- <span data-ttu-id="ae3ad-120">Matrice di sequenze</span><span class="sxs-lookup"><span data-stu-id="ae3ad-120">An array of sequences</span></span>
- <span data-ttu-id="ae3ad-121">Qualsiasi altra combinazione di sequenze enumerabili</span><span class="sxs-lookup"><span data-stu-id="ae3ad-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="ae3ad-122">Il codice seguente usa `Seq.concat` per illustrare gli scenari in grado di supportare utilizzando tipi flessibili.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="ae3ad-123">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="ae3ad-124">In F #, come in altri linguaggi orientati, vi sono contesti in cui i tipi derivati o tipi che implementano le interfacce vengono convertiti automaticamente in un tipo di base o un tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="ae3ad-125">Negli argomenti diretti, ma non quando il tipo è in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione o come argomento di tipo, si verificano queste conversioni automatico.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="ae3ad-126">Di conseguenza, la notazione di tipo flessibile è particolarmente utile quando il tipo a che si applica fa parte di un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="ae3ad-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae3ad-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae3ad-127">See Also</span></span>

[<span data-ttu-id="ae3ad-128">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ae3ad-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ae3ad-129">Generics</span><span class="sxs-lookup"><span data-stu-id="ae3ad-129">Generics</span></span>](generics/index.md)
