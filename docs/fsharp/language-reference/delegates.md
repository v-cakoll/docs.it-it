---
title: Delegati (F#)
description: 'Acquisire familiarità con i delegati in F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a><span data-ttu-id="155f8-103">Delegati</span><span class="sxs-lookup"><span data-stu-id="155f8-103">Delegates</span></span>

<span data-ttu-id="155f8-104">Un delegato rappresenta una chiamata di funzione come oggetto.</span><span class="sxs-lookup"><span data-stu-id="155f8-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="155f8-105">In F #, è in genere consigliabile utilizzare valori di funzione per rappresentare funzioni come valori di prima classe. Tuttavia, i delegati vengono utilizzati in .NET Framework e pertanto sono necessari quando si interagisce con le API che associno.</span><span class="sxs-lookup"><span data-stu-id="155f8-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="155f8-106">Potrebbe inoltre essere utilizzati quando creazione di librerie progettate per utilizzare da altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="155f8-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="155f8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155f8-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="155f8-108">Note</span><span class="sxs-lookup"><span data-stu-id="155f8-108">Remarks</span></span>
<span data-ttu-id="155f8-109">Nella sintassi precedente, `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="155f8-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="155f8-110">I tipi di argomento che sono rappresentati da `type1` vengono automaticamente sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="155f8-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="155f8-111">Ne consegue che per questo tipo è utilizzare una forma di tupla se gli argomenti della funzione di destinazione vengono sottoposti a currying e una tupla tra parentesi per gli argomenti che sono già sotto forma di tupla.</span><span class="sxs-lookup"><span data-stu-id="155f8-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="155f8-112">Currying automatico consente di rimuovere un set di parentesi, lasciando un argomento di tupla che corrisponda al metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="155f8-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="155f8-113">Vedere l'esempio di codice per la sintassi da utilizzare in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="155f8-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="155f8-114">I delegati possono essere allegati a valori di funzione di F # e statici o metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="155f8-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="155f8-115">I valori di funzione F # possono essere passati direttamente come argomenti per i costruttori di delegati.</span><span class="sxs-lookup"><span data-stu-id="155f8-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="155f8-116">Per un metodo statico, il delegato viene costruito utilizzando il nome della classe e il metodo.</span><span class="sxs-lookup"><span data-stu-id="155f8-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="155f8-117">Per un metodo di istanza, specificare l'istanza dell'oggetto e un metodo in un argomento.</span><span class="sxs-lookup"><span data-stu-id="155f8-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="155f8-118">In entrambi i casi, operatore di accesso ai membri (`.`) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="155f8-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="155f8-119">Il `Invoke` metodo nel tipo delegato chiama la funzione incapsulata.</span><span class="sxs-lookup"><span data-stu-id="155f8-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="155f8-120">Inoltre, i delegati possono essere passati come valori di funzione facendo riferimento al nome di metodo Invoke senza le parentesi.</span><span class="sxs-lookup"><span data-stu-id="155f8-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="155f8-121">Il codice seguente viene illustrata la sintassi per la creazione di delegati che rappresentano i vari metodi in una classe.</span><span class="sxs-lookup"><span data-stu-id="155f8-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="155f8-122">A seconda se il metodo è un metodo statico o un metodo di istanza e se questo dispone di argomenti nel formato tupla o sottoposte a currying, la sintassi per dichiarare e assegnare il delegato è leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="155f8-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="155f8-123">Il codice seguente vengono illustrate alcune delle diverse modalità che l'utilizzo di delegati.</span><span class="sxs-lookup"><span data-stu-id="155f8-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="155f8-124">L'output dell'esempio di codice precedente è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="155f8-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="155f8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155f8-125">See Also</span></span>
[<span data-ttu-id="155f8-126">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="155f8-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="155f8-127">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="155f8-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="155f8-128">Eventi</span><span class="sxs-lookup"><span data-stu-id="155f8-128">Events</span></span>](members/events.md)
