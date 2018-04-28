---
title: Interfacce (F#)
description: 'Informazioni su come le interfacce di F # specificare set di membri correlati che implementano le altre classi.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fa299a7e37d4e1e3800a02bf5a77831db9146daf
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="interfaces"></a><span data-ttu-id="c01ea-103">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c01ea-103">Interfaces</span></span>

<span data-ttu-id="c01ea-104">*Interfacce* specificare set di membri correlati che implementano le altre classi.</span><span class="sxs-lookup"><span data-stu-id="c01ea-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="c01ea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c01ea-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="c01ea-106">Note</span><span class="sxs-lookup"><span data-stu-id="c01ea-106">Remarks</span></span>
<span data-ttu-id="c01ea-107">Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che non vengono implementati membri.</span><span class="sxs-lookup"><span data-stu-id="c01ea-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="c01ea-108">Al contrario, tutti i membri astratti, come indicato dalla parola chiave `abstract`.</span><span class="sxs-lookup"><span data-stu-id="c01ea-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="c01ea-109">Non si specifica un corpo del metodo per i metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="c01ea-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="c01ea-110">Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come un metodo con il `default` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c01ea-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="c01ea-111">In questo modo è equivalente alla creazione di un metodo virtuale in una classe base in altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="c01ea-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="c01ea-112">Tale metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c01ea-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="c01ea-113">È facoltativamente possibile assegnare a ogni parametro del metodo un nome usando la normale sintassi F #:</span><span class="sxs-lookup"><span data-stu-id="c01ea-113">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="c01ea-114">Nel precedente `ISprintable` esempio, il `Print` metodo ha un solo parametro di tipo `string` con il nome `format`.</span><span class="sxs-lookup"><span data-stu-id="c01ea-114">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="c01ea-115">Esistono due modi per implementare le interfacce: tramite espressioni di oggetto e, utilizzando i tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="c01ea-115">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="c01ea-116">In entrambi i casi, l'espressione di tipo o un oggetto di classe fornisce corpi di metodo per i metodi astratti dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c01ea-116">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="c01ea-117">Le implementazioni sono specifiche di ogni tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c01ea-117">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="c01ea-118">Metodi di interfaccia su diversi tipi di conseguenza, potrebbero essere diversi da altro.</span><span class="sxs-lookup"><span data-stu-id="c01ea-118">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="c01ea-119">Le parole chiave `interface` e `end`, che contrassegna l'inizio e fine della definizione di sono facoltativi quando si utilizza la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="c01ea-119">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="c01ea-120">Se non si utilizzano queste parole chiave, il compilatore prova a dedurre se il tipo è una classe o un'interfaccia, analizzando i costrutti in uso.</span><span class="sxs-lookup"><span data-stu-id="c01ea-120">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="c01ea-121">Se si definisce un membro o utilizzare un'altra sintassi di classe, il tipo viene interpretato come una classe.</span><span class="sxs-lookup"><span data-stu-id="c01ea-121">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="c01ea-122">.NET nello stile di codifica consiste nell'iniziare tutte le interfacce con una lettera maiuscola `I`.</span><span class="sxs-lookup"><span data-stu-id="c01ea-122">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="c01ea-123">Implementazione delle interfacce usando i tipi di classe</span><span class="sxs-lookup"><span data-stu-id="c01ea-123">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="c01ea-124">È possibile implementare una o più interfacce in un tipo di classe utilizzando il `interface` (parola chiave), il nome dell'interfaccia e `with` (parola chiave), seguita dalle definizioni di membro di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c01ea-124">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="c01ea-125">Le implementazioni di interfaccia vengono ereditate, pertanto non è necessario che tutte le classi derivate reimplementare li.</span><span class="sxs-lookup"><span data-stu-id="c01ea-125">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="c01ea-126">Chiamata di metodi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="c01ea-126">Calling Interface Methods</span></span>
<span data-ttu-id="c01ea-127">Metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite qualsiasi oggetto di tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c01ea-127">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="c01ea-128">Di conseguenza, potrebbe essere necessario eseguire l'upcast al tipo di interfaccia utilizzando il `:>` operatore o `upcast` operatore per chiamare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="c01ea-128">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="c01ea-129">Per chiamare il metodo di interfaccia, quando si dispone di un oggetto di tipo `SomeClass`, è necessario eseguire l'upcast l'oggetto per il tipo di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c01ea-129">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="c01ea-130">Un'alternativa consiste nel dichiarare un metodo sull'oggetto di tale upcasts e chiama il metodo di interfaccia, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c01ea-130">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="c01ea-131">Implementazione di interfacce tramite espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="c01ea-131">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="c01ea-132">Espressioni di oggetto consentono di implementare un'interfaccia in modo breve.</span><span class="sxs-lookup"><span data-stu-id="c01ea-132">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="c01ea-133">E sono utili quando non è necessario creare un tipo denominato, e si desidera semplicemente un oggetto che supporta i metodi di interfaccia, senza metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c01ea-133">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="c01ea-134">Un'espressione di oggetto come illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c01ea-134">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="c01ea-135">Ereditarietà dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="c01ea-135">Interface Inheritance</span></span>
<span data-ttu-id="c01ea-136">Le interfacce possono ereditare da una o più interfacce base.</span><span class="sxs-lookup"><span data-stu-id="c01ea-136">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="c01ea-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c01ea-137">See Also</span></span>
[<span data-ttu-id="c01ea-138">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="c01ea-138">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="c01ea-139">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="c01ea-139">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="c01ea-140">Classi</span><span class="sxs-lookup"><span data-stu-id="c01ea-140">Classes</span></span>](classes.md)
