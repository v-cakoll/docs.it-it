---
title: Tipi flessibili
description: Informazioni su come usare F# l'annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore ha un tipo compatibile con un tipo specificato.
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083069"
---
# <a name="flexible-types"></a><span data-ttu-id="a8473-103">Tipi flessibili</span><span class="sxs-lookup"><span data-stu-id="a8473-103">Flexible Types</span></span>

<span data-ttu-id="a8473-104">Un' *annotazione di tipo flessibile* indica che un parametro, una variabile o un valore ha un tipo compatibile con un tipo specificato, in cui la compatibilità è determinata dalla posizione in una gerarchia orientata a oggetti di classi o interfacce.</span><span class="sxs-lookup"><span data-stu-id="a8473-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="a8473-105">I tipi flessibili sono utili in particolare quando la conversione automatica a tipi di livello superiore nella gerarchia dei tipi non si verifica, ma si desidera comunque abilitare la funzionalità per l'utilizzo di qualsiasi tipo nella gerarchia o di qualsiasi tipo che implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8473-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8473-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8473-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="a8473-107">Note</span><span class="sxs-lookup"><span data-stu-id="a8473-107">Remarks</span></span>

<span data-ttu-id="a8473-108">Nella sintassi precedente, *Type* rappresenta un tipo di base o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8473-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="a8473-109">Un tipo flessibile è equivalente a un tipo generico con un vincolo che limita i tipi consentiti ai tipi compatibili con il tipo di interfaccia o di base.</span><span class="sxs-lookup"><span data-stu-id="a8473-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="a8473-110">Ovvero le due righe di codice seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a8473-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="a8473-111">I tipi flessibili sono utili in diversi tipi di situazioni.</span><span class="sxs-lookup"><span data-stu-id="a8473-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="a8473-112">Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), spesso è utile che la funzione restituisca un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="a8473-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="a8473-113">Nell'esempio seguente, l'uso di un tipo flessibile con un argomento Sequence in `iterate2` consente alla funzione di ordine superiore di funzionare con le funzioni che generano sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="a8473-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="a8473-114">Si considerino le due funzioni seguenti, una delle quali restituisce una sequenza, l'altra delle quali restituisce un tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="a8473-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="a8473-115">Per un altro esempio, si consideri la funzione della libreria [Seq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) :</span><span class="sxs-lookup"><span data-stu-id="a8473-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="a8473-116">È possibile passare una qualsiasi delle sequenze enumerabili seguenti a questa funzione:</span><span class="sxs-lookup"><span data-stu-id="a8473-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="a8473-117">Elenco di elenchi</span><span class="sxs-lookup"><span data-stu-id="a8473-117">A list of lists</span></span>
- <span data-ttu-id="a8473-118">Elenco di matrici</span><span class="sxs-lookup"><span data-stu-id="a8473-118">A list of arrays</span></span>
- <span data-ttu-id="a8473-119">Matrice di elenchi</span><span class="sxs-lookup"><span data-stu-id="a8473-119">An array of lists</span></span>
- <span data-ttu-id="a8473-120">Una matrice di sequenze</span><span class="sxs-lookup"><span data-stu-id="a8473-120">An array of sequences</span></span>
- <span data-ttu-id="a8473-121">Qualsiasi altra combinazione di sequenze enumerabili</span><span class="sxs-lookup"><span data-stu-id="a8473-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="a8473-122">Il codice seguente usa `Seq.concat` per illustrare gli scenari che è possibile supportare con i tipi flessibili.</span><span class="sxs-lookup"><span data-stu-id="a8473-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="a8473-123">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a8473-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="a8473-124">In F#, come in altri linguaggi orientati a oggetti, esistono contesti in cui i tipi derivati o i tipi che implementano le interfacce vengono convertiti automaticamente in un tipo di base o di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8473-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="a8473-125">Queste conversioni automatiche si verificano negli argomenti diretti, ma non quando il tipo si trova in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione, o come argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8473-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="a8473-126">Pertanto, la notazione flessibile del tipo è particolarmente utile quando il tipo a cui si sta applicando fa parte di un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="a8473-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8473-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8473-127">See also</span></span>

- [<span data-ttu-id="a8473-128">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="a8473-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a8473-129">Generics</span><span class="sxs-lookup"><span data-stu-id="a8473-129">Generics</span></span>](./generics/index.md)
