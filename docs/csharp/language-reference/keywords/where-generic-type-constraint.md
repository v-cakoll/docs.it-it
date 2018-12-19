---
title: where (vincolo di tipo generico) - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 8d6c1fba87ef1c4344bd150b2af2f5d1ad019695
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235715"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="4b5a9-102">where (vincolo di tipo generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4b5a9-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="4b5a9-103">La clausola `where` in una definizione generica specifica i vincoli per i tipi che vengono usati come argomenti per i parametri di tipo in un tipo generico, metodo, delegato o funzione locale.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="4b5a9-104">I vincoli possono specificare interfacce, classi di base o richiedere che un tipo generico sia un riferimento, un valore o un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value or unmanaged type.</span></span> <span data-ttu-id="4b5a9-105">Dichiarano le funzionalità che l'argomento tipo deve possedere.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="4b5a9-106">Ad esempio, una classe generica, `MyGenericClass`, può essere dichiarata in modo che tramite il parametro di tipo `T` venga implementata l'interfaccia <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="4b5a9-107">Per altre informazioni sulla clausola where in un'espressione di query, vedere [Clausola where](where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4b5a9-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="4b5a9-108">La clausola `where` può inoltre includere un vincolo di classe di base.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="4b5a9-109">Il vincolo di classe di base dichiara che un tipo da usare come argomento tipo per quel tipo generico usi la classe specificata come classe di base (o sia quella classe di base) come argomento tipo per quel tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="4b5a9-110">Se viene usato il vincolo della classe di base, deve apparire prima di tutti gli altri vincoli per quel parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="4b5a9-111">Alcuni tipi non sono consentiti come vincoli di classe di base: <xref:System.Object>, <xref:System.Array> e <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="4b5a9-112">Prima di C# 7.3 anche <xref:System.Enum>, <xref:System.Delegate> e <xref:System.MulticastDelegate> non erano consentiti come vincoli di classe di base.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="4b5a9-113">L'esempio seguente illustra i tipi possono ora essere specificati come una classe di base:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="4b5a9-114">La clausola `where` può specificare che il tipo è un oggetto `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="4b5a9-115">Il vincolo `struct` elimina la necessità di specificare un vincolo di classe di base di `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="4b5a9-116">Il tipo `System.ValueType` non può essere usato come vincolo di classe di base.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="4b5a9-117">Nell'esempio seguente vengono illustrati i vincoli `class` e `struct`:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="4b5a9-118">La clausola `where` può anche includere un vincolo `unmanaged`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-118">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="4b5a9-119">Il vincolo `unmanaged` limita il parametro di tipo ai tipi noti come **tipi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-119">The `unmanaged` constraint limits the type parameter to types known as **unmanaged types**.</span></span> <span data-ttu-id="4b5a9-120">Un **tipo non gestito** è un tipo che non è un tipo riferimento e non contiene campi di tipi riferimento a nessun livello di annidamento.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-120">An **unmanaged type** is a type that isn't a reference type and doesn't contain reference type fields at any level of nesting.</span></span> <span data-ttu-id="4b5a9-121">Il vincolo `unmanaged` rende più semplice la scrittura di codice di interoperabilità di basso livello in C#.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-121">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="4b5a9-122">Questo vincolo abilita le routine riutilizzabili in tutti i tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-122">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="4b5a9-123">Il vincolo `unmanaged` non può essere combinato con il vincolo `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-123">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="4b5a9-124">Il vincolo `unmanaged` impone che il tipo deve essere un elemento `struct`:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-124">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="4b5a9-125">La clausola `where` può anche includere un vincolo di costruttore, `new()`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-125">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="4b5a9-126">Tale vincolo consente di creare un'istanza di un parametro di tipo usando l'operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-126">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="4b5a9-127">Il [vincolo new()](new-constraint.md) consente al compilatore di sapere che ogni argomento di tipo specificato deve usare un costruttore accessibile senza parametri o predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-127">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="4b5a9-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-128">For example:</span></span>

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="4b5a9-129">Il vincolo `new()` viene visualizzato per ultimo nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-129">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="4b5a9-130">Il vincolo `new()` non può essere combinato con i vincoli `struct` o `unmanaged`.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-130">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="4b5a9-131">Tutti i tipi che soddisfano i vincoli devono avere un costruttore senza parametri accessibile, per rendere il vincolo `new()` ridondante.</span><span class="sxs-lookup"><span data-stu-id="4b5a9-131">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="4b5a9-132">Con più parametri di tipo, usare una clausola `where` per ogni parametro di tipo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-132">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="4b5a9-133">È anche possibile associare vincoli ai parametri di tipo di metodi generici, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-133">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="4b5a9-134">Si noti che la sintassi usata per descrivere i vincoli dei parametri di tipo per i delegati è uguale a quella dei metodi:</span><span class="sxs-lookup"><span data-stu-id="4b5a9-134">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="4b5a9-135">Per informazioni sui delegati generici, vedere [Delegati generici](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4b5a9-135">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="4b5a9-136">Per informazioni dettagliate sulla sintassi e sull'uso dei vincoli, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4b5a9-136">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4b5a9-137">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4b5a9-137">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4b5a9-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b5a9-138">See also</span></span>

- [<span data-ttu-id="4b5a9-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4b5a9-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4b5a9-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4b5a9-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4b5a9-141">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="4b5a9-141">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [<span data-ttu-id="4b5a9-142">Vincolo new</span><span class="sxs-lookup"><span data-stu-id="4b5a9-142">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
- [<span data-ttu-id="4b5a9-143">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4b5a9-143">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
