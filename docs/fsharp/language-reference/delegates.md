---
title: Delegati
description: Informazioni su come usare i delegati in F#.
ms.date: 05/16/2016
ms.openlocfilehash: 772685488b7caef92123979d817929c631248afb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766077"
---
# <a name="delegates"></a><span data-ttu-id="41c70-103">Delegati</span><span class="sxs-lookup"><span data-stu-id="41c70-103">Delegates</span></span>

<span data-ttu-id="41c70-104">Un delegato rappresenta una chiamata di funzione come oggetto.</span><span class="sxs-lookup"><span data-stu-id="41c70-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="41c70-105">In F#, è in genere consigliabile usare valori di funzione per rappresentare funzioni come valori di prima classe. Tuttavia, i delegati vengono usati in .NET Framework e pertanto sono necessari quando si interagisce con le API che prevedono li.</span><span class="sxs-lookup"><span data-stu-id="41c70-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="41c70-106">È possibile usarle anche quando creazione di librerie progettate per utilizzare da altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41c70-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="41c70-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41c70-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="41c70-108">Note</span><span class="sxs-lookup"><span data-stu-id="41c70-108">Remarks</span></span>

<span data-ttu-id="41c70-109">Nella sintassi precedente `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="41c70-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="41c70-110">I tipi di argomento che sono rappresentati da `type1` automaticamente vengono sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="41c70-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="41c70-111">Ne consegue che per questo tipo è usare un formato di tupla se gli argomenti della funzione di destinazione vengono sottoposti a currying e una tupla tra parentesi per gli argomenti che è già in formato tupla.</span><span class="sxs-lookup"><span data-stu-id="41c70-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="41c70-112">Il currying automatica rimuove un set di parentesi, lasciando un argomento con tuple che corrisponde al metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="41c70-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="41c70-113">Vedere l'esempio di codice per la sintassi da utilizzare in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="41c70-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="41c70-114">I delegati possono essere collegati a F# funzione di valori e statici o metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="41c70-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="41c70-115">F#valori di funzione possono essere passati direttamente come argomenti al delegato costruttori.</span><span class="sxs-lookup"><span data-stu-id="41c70-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="41c70-116">Per un metodo statico, il delegato viene costruito usando il nome della classe e il metodo.</span><span class="sxs-lookup"><span data-stu-id="41c70-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="41c70-117">Per un metodo di istanza, specificare l'istanza dell'oggetto e un metodo in un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="41c70-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="41c70-118">In entrambi i casi, operatore di accesso ai membri (`.`) viene usato.</span><span class="sxs-lookup"><span data-stu-id="41c70-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="41c70-119">Il `Invoke` metodo sul tipo di delegato chiama la funzione incapsulata.</span><span class="sxs-lookup"><span data-stu-id="41c70-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="41c70-120">Inoltre, i delegati renserlo passabile come valori di funzioni per fare riferimento al nome di metodo Invoke senza le parentesi.</span><span class="sxs-lookup"><span data-stu-id="41c70-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="41c70-121">Il codice seguente illustra la sintassi per la creazione di delegati che rappresentano i vari metodi in una classe.</span><span class="sxs-lookup"><span data-stu-id="41c70-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="41c70-122">A seconda se il metodo è un metodo statico o un metodo di istanza e se questo dispone di argomenti nel modulo sottoposti a currying o il formato di tupla, la sintassi di dichiarazione e l'assegnazione del delegato è leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="41c70-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="41c70-123">Il codice seguente illustra alcuni modi diversi che è possibile usare i delegati.</span><span class="sxs-lookup"><span data-stu-id="41c70-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="41c70-124">L'output dell'esempio di codice precedente è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="41c70-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="41c70-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41c70-125">See also</span></span>

- [<span data-ttu-id="41c70-126">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="41c70-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="41c70-127">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="41c70-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="41c70-128">Eventi</span><span class="sxs-lookup"><span data-stu-id="41c70-128">Events</span></span>](members/events.md)