---
title: Vincoli (F#)
description: 'Informazioni sui vincoli di F # che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.'
ms.date: 05/16/2016
ms.openlocfilehash: 9534db4ffd195022366af8c993658bd94f375f53
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531944"
---
# <a name="constraints"></a><span data-ttu-id="318b7-103">Vincoli</span><span class="sxs-lookup"><span data-stu-id="318b7-103">Constraints</span></span>

<span data-ttu-id="318b7-104">In questo argomento descrive i vincoli che è possibile applicare generico parametri per specificare i requisiti per un argomento di tipo in un tipo generico o una funzione di tipo.</span><span class="sxs-lookup"><span data-stu-id="318b7-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="318b7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="318b7-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="318b7-106">Note</span><span class="sxs-lookup"><span data-stu-id="318b7-106">Remarks</span></span>

<span data-ttu-id="318b7-107">Esistono diversi vincoli diversi, che è possibile applicare per limitare i tipi che possono essere utilizzati in un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="318b7-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="318b7-108">Nella tabella seguente elenca e descrive questi vincoli.</span><span class="sxs-lookup"><span data-stu-id="318b7-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="318b7-109">Vincolo</span><span class="sxs-lookup"><span data-stu-id="318b7-109">Constraint</span></span>|<span data-ttu-id="318b7-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="318b7-110">Syntax</span></span>|<span data-ttu-id="318b7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="318b7-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="318b7-112">Vincolo di tipo</span><span class="sxs-lookup"><span data-stu-id="318b7-112">Type Constraint</span></span>|<span data-ttu-id="318b7-113">*parametro di tipo* :&gt; *tipo*</span><span class="sxs-lookup"><span data-stu-id="318b7-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="318b7-114">Il tipo specificato deve essere uguale o derivare dal tipo specificato o, se il tipo è un'interfaccia, il tipo specificato deve implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="318b7-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="318b7-115">Vincolo Null</span><span class="sxs-lookup"><span data-stu-id="318b7-115">Null Constraint</span></span>|<span data-ttu-id="318b7-116">*parametro di tipo* : null</span><span class="sxs-lookup"><span data-stu-id="318b7-116">*type-parameter* : null</span></span>|<span data-ttu-id="318b7-117">Il tipo specificato deve supportare il valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="318b7-117">The provided type must support the null literal.</span></span> <span data-ttu-id="318b7-118">Ciò include tutti i tipi di oggetti .NET ma non F # elenco, tupla, funzione, classe, record o i tipi di unione.</span><span class="sxs-lookup"><span data-stu-id="318b7-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="318b7-119">Vincolo membro esplicito</span><span class="sxs-lookup"><span data-stu-id="318b7-119">Explicit Member Constraint</span></span>|<span data-ttu-id="318b7-120">[(]*parametro di tipo* [or... o *parametro di tipo*)]: (*firma del membro*)</span><span class="sxs-lookup"><span data-stu-id="318b7-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="318b7-121">Almeno uno degli argomenti di tipo specificati deve avere un membro con la firma specificata. non destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="318b7-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="318b7-122">I membri devono essere esplicitamente definiti sul tipo o parte di un'estensione di tipo implicito da destinazioni valide per un vincolo membro esplicito.</span><span class="sxs-lookup"><span data-stu-id="318b7-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="318b7-123">Vincolo del costruttore</span><span class="sxs-lookup"><span data-stu-id="318b7-123">Constructor Constraint</span></span>|<span data-ttu-id="318b7-124">*parametro di tipo* : (new: unità -&gt; ' un)</span><span class="sxs-lookup"><span data-stu-id="318b7-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="318b7-125">Il tipo specificato deve avere un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="318b7-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="318b7-126">Vincolo di tipo valore</span><span class="sxs-lookup"><span data-stu-id="318b7-126">Value Type Constraint</span></span>|<span data-ttu-id="318b7-127">: uno struct</span><span class="sxs-lookup"><span data-stu-id="318b7-127">: struct</span></span>|<span data-ttu-id="318b7-128">Il tipo specificato deve essere un tipo di valore .NET.</span><span class="sxs-lookup"><span data-stu-id="318b7-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="318b7-129">Vincolo di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="318b7-129">Reference Type Constraint</span></span>|<span data-ttu-id="318b7-130">: non struct</span><span class="sxs-lookup"><span data-stu-id="318b7-130">: not struct</span></span>|<span data-ttu-id="318b7-131">Il tipo specificato deve essere un tipo di riferimento .NET.</span><span class="sxs-lookup"><span data-stu-id="318b7-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="318b7-132">Vincolo di tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="318b7-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="318b7-133">: enumerazione&lt;*tipo sottostante*&gt;</span><span class="sxs-lookup"><span data-stu-id="318b7-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="318b7-134">Il tipo specificato deve essere un tipo enumerato che contiene il tipo sottostante specificato. non destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="318b7-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="318b7-135">Vincolo di delegato</span><span class="sxs-lookup"><span data-stu-id="318b7-135">Delegate Constraint</span></span>|<span data-ttu-id="318b7-136">: delegare&lt;*-parametri-tipo di tupla*, *tipo restituito*&gt;</span><span class="sxs-lookup"><span data-stu-id="318b7-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="318b7-137">Il tipo specificato deve essere un tipo delegato che contiene gli argomenti specificati e restituire valore. non destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="318b7-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="318b7-138">Vincolo di confronto</span><span class="sxs-lookup"><span data-stu-id="318b7-138">Comparison Constraint</span></span>|<span data-ttu-id="318b7-139">: confronto</span><span class="sxs-lookup"><span data-stu-id="318b7-139">: comparison</span></span>|<span data-ttu-id="318b7-140">Il tipo specificato deve supportare il confronto.</span><span class="sxs-lookup"><span data-stu-id="318b7-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="318b7-141">Vincolo di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="318b7-141">Equality Constraint</span></span>|<span data-ttu-id="318b7-142">: uguaglianza</span><span class="sxs-lookup"><span data-stu-id="318b7-142">: equality</span></span>|<span data-ttu-id="318b7-143">Il tipo specificato deve supportare l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="318b7-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="318b7-144">Vincolo non gestito</span><span class="sxs-lookup"><span data-stu-id="318b7-144">Unmanaged Constraint</span></span>|<span data-ttu-id="318b7-145">: non gestito</span><span class="sxs-lookup"><span data-stu-id="318b7-145">: unmanaged</span></span>|<span data-ttu-id="318b7-146">Il tipo specificato deve essere un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="318b7-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="318b7-147">Tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), tipi di enumerazione `nativeptr<_>`, o una struttura non generica i cui campi sono tutti i tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="318b7-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="318b7-148">È necessario aggiungere un vincolo quando il codice deve usare una funzionalità che è disponibile per il tipo di vincolo ma non nei tipi in generale.</span><span class="sxs-lookup"><span data-stu-id="318b7-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="318b7-149">Ad esempio, se si usa il vincolo di tipo per specificare un tipo di classe, è possibile usare uno dei metodi della classe della funzione generica o tipo.</span><span class="sxs-lookup"><span data-stu-id="318b7-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="318b7-150">I vincoli è talvolta necessario specificare durante la scrittura di parametri di tipo in modo esplicito, poiché senza un vincolo, il compilatore non ha modo di verificare che le funzionalità che si siano utilizzando sarà disponibile in qualsiasi tipo che può essere fornito in fase di esecuzione per il tipo parametro.</span><span class="sxs-lookup"><span data-stu-id="318b7-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="318b7-151">I vincoli più comuni che è usare nel codice F # sono vincoli di tipo specificare classi base o interfacce.</span><span class="sxs-lookup"><span data-stu-id="318b7-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="318b7-152">Gli altri vincoli vengono utilizzati dalla libreria di F # per implementare determinate funzionalità, ad esempio il vincolo membro esplicito, che viene usato per implementare l'overload di operatori per gli operatori aritmetici o viene fornito principalmente perché F # supporta completo set di vincoli è supportata da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="318b7-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="318b7-153">Durante il processo di inferenza del tipo, alcuni vincoli vengono automaticamente dedotti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="318b7-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="318b7-154">Ad esempio, se si usa il `+` operatore in una funzione, il compilatore deduce automaticamente di un vincolo per tipi di variabili utilizzate nell'espressione di membro esplicito.</span><span class="sxs-lookup"><span data-stu-id="318b7-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="318b7-155">Il codice seguente illustra alcune dichiarazioni di vincolo.</span><span class="sxs-lookup"><span data-stu-id="318b7-155">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="318b7-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="318b7-156">See also</span></span>

- [<span data-ttu-id="318b7-157">Generics</span><span class="sxs-lookup"><span data-stu-id="318b7-157">Generics</span></span>](index.md)
- [<span data-ttu-id="318b7-158">Vincoli</span><span class="sxs-lookup"><span data-stu-id="318b7-158">Constraints</span></span>](constraints.md)
