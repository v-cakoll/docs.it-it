---
title: Delegati (F#)
description: "Acquisire familiarità con i delegati in F #."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="3a8f3-104">Delegati</span><span class="sxs-lookup"><span data-stu-id="3a8f3-104">Delegates</span></span>

<span data-ttu-id="3a8f3-105">Un delegato rappresenta una chiamata di funzione come oggetto.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-105">A delegate represents a function call as an object.</span></span> <span data-ttu-id="3a8f3-106">In F #, è in genere consigliabile utilizzare valori di funzione per rappresentare funzioni come valori di prima classe. Tuttavia, i delegati vengono utilizzati in .NET Framework e pertanto sono necessari quando si interagisce con le API che associno.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-106">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="3a8f3-107">Potrebbe inoltre essere utilizzati quando creazione di librerie progettate per utilizzare da altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-107">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="3a8f3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a8f3-108">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="3a8f3-109">Note</span><span class="sxs-lookup"><span data-stu-id="3a8f3-109">Remarks</span></span>
<span data-ttu-id="3a8f3-110">Nella sintassi precedente, `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-110">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="3a8f3-111">I tipi di argomento che sono rappresentati da `type1` vengono automaticamente sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-111">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="3a8f3-112">Ne consegue che per questo tipo è utilizzare una forma di tupla se gli argomenti della funzione di destinazione vengono sottoposti a currying e una tupla tra parentesi per gli argomenti che sono già sotto forma di tupla.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-112">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="3a8f3-113">Currying automatico consente di rimuovere un set di parentesi, lasciando un argomento di tupla che corrisponda al metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-113">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="3a8f3-114">Vedere l'esempio di codice per la sintassi da utilizzare in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-114">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="3a8f3-115">I delegati possono essere allegati a valori di funzione di F # e statici o metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-115">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="3a8f3-116">I valori di funzione F # possono essere passati direttamente come argomenti per i costruttori di delegati.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-116">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="3a8f3-117">Per un metodo statico, il delegato viene costruito utilizzando il nome della classe e il metodo.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-117">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="3a8f3-118">Per un metodo di istanza, specificare l'istanza dell'oggetto e un metodo in un argomento.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-118">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="3a8f3-119">In entrambi i casi, operatore di accesso ai membri (`.`) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-119">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="3a8f3-120">Il `Invoke` metodo nel tipo delegato chiama la funzione incapsulata.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-120">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="3a8f3-121">Inoltre, i delegati possono essere passati come valori di funzione facendo riferimento al nome di metodo Invoke senza le parentesi.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-121">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="3a8f3-122">Il codice seguente viene illustrata la sintassi per la creazione di delegati che rappresentano i vari metodi in una classe.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-122">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="3a8f3-123">A seconda se il metodo è un metodo statico o un metodo di istanza e se questo dispone di argomenti nel formato tupla o sottoposte a currying, la sintassi per dichiarare e assegnare il delegato è leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-123">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="3a8f3-124">Il codice seguente vengono illustrate alcune delle diverse modalità che l'utilizzo di delegati.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-124">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="3a8f3-125">L'output dell'esempio di codice precedente è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a8f3-125">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="3a8f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a8f3-126">See Also</span></span>
[<span data-ttu-id="3a8f3-127">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="3a8f3-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="3a8f3-128">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="3a8f3-128">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="3a8f3-129">Eventi</span><span class="sxs-lookup"><span data-stu-id="3a8f3-129">Events</span></span>](members/events.md)
