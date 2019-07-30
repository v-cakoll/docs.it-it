---
title: Interfacce
description: Informazioni su F# come le interfacce specificano i set di membri correlati che altre classi implementano.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627656"
---
# <a name="interfaces"></a><span data-ttu-id="9df60-103">Interfacce</span><span class="sxs-lookup"><span data-stu-id="9df60-103">Interfaces</span></span>

<span data-ttu-id="9df60-104">Le *interfacce* specificano set di membri correlati implementati da altre classi.</span><span class="sxs-lookup"><span data-stu-id="9df60-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="9df60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9df60-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
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

## <a name="remarks"></a><span data-ttu-id="9df60-106">Note</span><span class="sxs-lookup"><span data-stu-id="9df60-106">Remarks</span></span>

<span data-ttu-id="9df60-107">Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che nessun membro viene implementato.</span><span class="sxs-lookup"><span data-stu-id="9df60-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="9df60-108">Al contrario, tutti i membri sono astratti, come indicato dalla `abstract`parola chiave.</span><span class="sxs-lookup"><span data-stu-id="9df60-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="9df60-109">Non viene fornito il corpo di un metodo per i metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="9df60-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="9df60-110">Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come metodo insieme alla `default` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="9df60-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="9df60-111">Questa operazione equivale alla creazione di un metodo virtuale in una classe base in altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="9df60-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="9df60-112">Questo metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9df60-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="9df60-113">L'accessibilità predefinita per le `public`interfacce è.</span><span class="sxs-lookup"><span data-stu-id="9df60-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="9df60-114">Facoltativamente, è possibile assegnare un nome a ogni parametro di F# metodo usando la sintassi normale:</span><span class="sxs-lookup"><span data-stu-id="9df60-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="9df60-115">Nell'esempio precedente `ISprintable` , il `Print` metodo dispone di un solo parametro del tipo `string` con il nome `format`.</span><span class="sxs-lookup"><span data-stu-id="9df60-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="9df60-116">Esistono due modi per implementare le interfacce: usando le espressioni di oggetto e usando i tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="9df60-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="9df60-117">In entrambi i casi, il tipo di classe o l'espressione di oggetto fornisce corpi del metodo per i metodi astratti dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9df60-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="9df60-118">Le implementazioni sono specifiche per ogni tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9df60-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="9df60-119">Pertanto, i metodi di interfaccia su tipi diversi potrebbero essere diversi tra loro.</span><span class="sxs-lookup"><span data-stu-id="9df60-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="9df60-120">Le parole `interface` chiave `end`e, che contrassegnano l'inizio e la fine della definizione, sono facoltative quando si usa la sintassi Lightweight.</span><span class="sxs-lookup"><span data-stu-id="9df60-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="9df60-121">Se non si utilizzano queste parole chiave, il compilatore tenta di dedurre se il tipo è una classe o un'interfaccia analizzando i costrutti utilizzati.</span><span class="sxs-lookup"><span data-stu-id="9df60-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="9df60-122">Se si definisce un membro o si utilizza un'altra sintassi della classe, il tipo viene interpretato come una classe.</span><span class="sxs-lookup"><span data-stu-id="9df60-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="9df60-123">Lo stile di codifica .NET prevede l'avvio di tutte le interfacce `I`con una maiuscola.</span><span class="sxs-lookup"><span data-stu-id="9df60-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="9df60-124">Implementazione di interfacce tramite tipi di classe</span><span class="sxs-lookup"><span data-stu-id="9df60-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="9df60-125">È possibile implementare una o più interfacce in un tipo di classe usando la `interface` parola chiave, il nome dell'interfaccia e la `with` parola chiave, seguita dalle definizioni dei membri di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9df60-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="9df60-126">Le implementazioni dell'interfaccia vengono ereditate, pertanto le classi derivate non devono essere reimplementate.</span><span class="sxs-lookup"><span data-stu-id="9df60-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="9df60-127">Chiamata di metodi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="9df60-127">Calling Interface Methods</span></span>

<span data-ttu-id="9df60-128">I metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite alcun oggetto del tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9df60-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="9df60-129">Quindi, potrebbe essere necessario eseguire il cast al tipo di interfaccia usando l' `:>` operatore o l' `upcast` operatore per chiamare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="9df60-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="9df60-130">Per chiamare il metodo di interfaccia quando si dispone di un oggetto `SomeClass`di tipo, è necessario eseguire il cast dell'oggetto al tipo di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9df60-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="9df60-131">In alternativa, è possibile dichiarare un metodo sull'oggetto che esegue il cast e chiama il metodo di interfaccia, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9df60-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="9df60-132">Implementazione di interfacce tramite espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="9df60-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="9df60-133">Le espressioni di oggetto forniscono un metodo breve per implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9df60-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="9df60-134">Sono utili quando non è necessario creare un tipo denominato e si vuole solo un oggetto che supporta i metodi di interfaccia, senza metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9df60-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="9df60-135">Nel codice seguente viene illustrata un'espressione di oggetto.</span><span class="sxs-lookup"><span data-stu-id="9df60-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="9df60-136">Ereditarietà dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="9df60-136">Interface Inheritance</span></span>

<span data-ttu-id="9df60-137">Le interfacce possono ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="9df60-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="9df60-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9df60-138">See also</span></span>

- [<span data-ttu-id="9df60-139">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="9df60-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9df60-140">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="9df60-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="9df60-141">Classi</span><span class="sxs-lookup"><span data-stu-id="9df60-141">Classes</span></span>](classes.md)
