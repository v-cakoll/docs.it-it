---
title: Delegati
description: Informazioni su come usare i delegati in F#.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630365"
---
# <a name="delegates"></a><span data-ttu-id="ee55a-103">Delegati</span><span class="sxs-lookup"><span data-stu-id="ee55a-103">Delegates</span></span>

<span data-ttu-id="ee55a-104">Un delegato rappresenta una chiamata di funzione come un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ee55a-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="ee55a-105">In F#, in genere è necessario utilizzare i valori di funzione per rappresentare le funzioni come valori di prima classe; Tuttavia, i delegati vengono usati nell'.NET Framework e pertanto sono necessari quando si interagisce con le API che li prevedono.</span><span class="sxs-lookup"><span data-stu-id="ee55a-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="ee55a-106">Possono anche essere usati durante la creazione di librerie progettate per l'uso da altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ee55a-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee55a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee55a-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="ee55a-108">Note</span><span class="sxs-lookup"><span data-stu-id="ee55a-108">Remarks</span></span>

<span data-ttu-id="ee55a-109">Nella sintassi precedente, `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="ee55a-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="ee55a-110">I tipi di argomento rappresentati da `type1` vengono sottoposti a currying automatico.</span><span class="sxs-lookup"><span data-stu-id="ee55a-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="ee55a-111">Questo suggerisce che per questo tipo si usa un form di tupla se gli argomenti della funzione di destinazione sono sottoposti a currying e una tupla tra parentesi per gli argomenti già presenti nel form della tupla.</span><span class="sxs-lookup"><span data-stu-id="ee55a-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="ee55a-112">Il currying automatico rimuove un set di parentesi, lasciando un argomento di tupla corrispondente al metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ee55a-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="ee55a-113">Fare riferimento all'esempio di codice per la sintassi da usare in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="ee55a-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="ee55a-114">I delegati possono F# essere associati a valori di funzione e metodi statici o di istanza.</span><span class="sxs-lookup"><span data-stu-id="ee55a-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="ee55a-115">F#i valori della funzione possono essere passati direttamente come argomenti ai costruttori delegati.</span><span class="sxs-lookup"><span data-stu-id="ee55a-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="ee55a-116">Per un metodo statico, il delegato viene costruito usando il nome della classe e il metodo.</span><span class="sxs-lookup"><span data-stu-id="ee55a-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="ee55a-117">Per un metodo di istanza, è necessario specificare l'istanza e il metodo dell'oggetto in un argomento.</span><span class="sxs-lookup"><span data-stu-id="ee55a-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="ee55a-118">In entrambi i casi, viene usato l'operatore`.`di accesso ai membri ().</span><span class="sxs-lookup"><span data-stu-id="ee55a-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="ee55a-119">Il `Invoke` metodo nel tipo delegato chiama la funzione incapsulata.</span><span class="sxs-lookup"><span data-stu-id="ee55a-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="ee55a-120">Inoltre, i delegati possono essere passati come valori di funzione facendo riferimento al nome del metodo Invoke senza le parentesi.</span><span class="sxs-lookup"><span data-stu-id="ee55a-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="ee55a-121">Nel codice seguente viene illustrata la sintassi per la creazione di delegati che rappresentano i vari metodi di una classe.</span><span class="sxs-lookup"><span data-stu-id="ee55a-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="ee55a-122">A seconda se il metodo è un metodo statico o un metodo di istanza e se dispone di argomenti nel form della tupla o nel form sottoposto a currying, la sintassi per la dichiarazione e l'assegnazione del delegato è leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="ee55a-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="ee55a-123">Il codice seguente illustra alcuni dei diversi modi in cui è possibile lavorare con i delegati.</span><span class="sxs-lookup"><span data-stu-id="ee55a-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="ee55a-124">L'output dell'esempio di codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="ee55a-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="ee55a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee55a-125">See also</span></span>

- [<span data-ttu-id="ee55a-126">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ee55a-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ee55a-127">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="ee55a-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="ee55a-128">Eventi</span><span class="sxs-lookup"><span data-stu-id="ee55a-128">Events</span></span>](./members/events.md)
