---
title: Vincoli (F#)
description: 'Informazioni sui vincoli di F # che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a><span data-ttu-id="03625-104">Vincoli</span><span class="sxs-lookup"><span data-stu-id="03625-104">Constraints</span></span>

<span data-ttu-id="03625-105">In questo argomento descrive i vincoli da applicare all'oggetto generico parametri per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico di tipo.</span><span class="sxs-lookup"><span data-stu-id="03625-105">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="03625-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03625-106">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="03625-107">Note</span><span class="sxs-lookup"><span data-stu-id="03625-107">Remarks</span></span>
<span data-ttu-id="03625-108">Sono disponibili diversi vincoli che è possibile applicare per limitare i tipi che possono essere usati in un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="03625-108">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="03625-109">Nella tabella seguente elenca e descrive questi vincoli.</span><span class="sxs-lookup"><span data-stu-id="03625-109">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="03625-110">Vincolo</span><span class="sxs-lookup"><span data-stu-id="03625-110">Constraint</span></span>|<span data-ttu-id="03625-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03625-111">Syntax</span></span>|<span data-ttu-id="03625-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03625-112">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="03625-113">Vincolo di tipo</span><span class="sxs-lookup"><span data-stu-id="03625-113">Type Constraint</span></span>|<span data-ttu-id="03625-114">*parametro di tipo* :&gt; *tipo*</span><span class="sxs-lookup"><span data-stu-id="03625-114">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="03625-115">Il tipo fornito deve essere uguale o derivare dal tipo specificato o se il tipo è un'interfaccia, il tipo fornito deve implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="03625-115">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="03625-116">Vincolo Null</span><span class="sxs-lookup"><span data-stu-id="03625-116">Null Constraint</span></span>|<span data-ttu-id="03625-117">*parametro di tipo* : null</span><span class="sxs-lookup"><span data-stu-id="03625-117">*type-parameter* : null</span></span>|<span data-ttu-id="03625-118">Il tipo fornito deve supportare il valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="03625-118">The provided type must support the null literal.</span></span> <span data-ttu-id="03625-119">Sono inclusi tutti i tipi di oggetti .NET ma non F # elenco, tupla, funzione, classe, record o i tipi di unione.</span><span class="sxs-lookup"><span data-stu-id="03625-119">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="03625-120">Vincolo di membro esplicito</span><span class="sxs-lookup"><span data-stu-id="03625-120">Explicit Member Constraint</span></span>|<span data-ttu-id="03625-121">[()]*parametro di tipo* [or... o *parametro di tipo*)]: (* membro firma *)</span><span class="sxs-lookup"><span data-stu-id="03625-121">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="03625-122">Almeno uno degli argomenti di tipo forniti deve avere un membro con la firma specificata. non può essere usata più comune.</span><span class="sxs-lookup"><span data-stu-id="03625-122">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="03625-123">I membri devono essere in modo esplicito definiti nel tipo o parte di un'estensione di tipo implicito per essere destinazioni valide per un vincolo di membro esplicito.</span><span class="sxs-lookup"><span data-stu-id="03625-123">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="03625-124">Vincolo del costruttore</span><span class="sxs-lookup"><span data-stu-id="03625-124">Constructor Constraint</span></span>|<span data-ttu-id="03625-125">*parametro di tipo* : (new: unità -&gt; ' un)</span><span class="sxs-lookup"><span data-stu-id="03625-125">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="03625-126">Il tipo specificato deve avere un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="03625-126">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="03625-127">Vincolo di tipo valore</span><span class="sxs-lookup"><span data-stu-id="03625-127">Value Type Constraint</span></span>|<span data-ttu-id="03625-128">: struct</span><span class="sxs-lookup"><span data-stu-id="03625-128">: struct</span></span>|<span data-ttu-id="03625-129">Il tipo fornito deve essere un tipo di valore .NET.</span><span class="sxs-lookup"><span data-stu-id="03625-129">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="03625-130">Vincolo di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="03625-130">Reference Type Constraint</span></span>|<span data-ttu-id="03625-131">: non struct</span><span class="sxs-lookup"><span data-stu-id="03625-131">: not struct</span></span>|<span data-ttu-id="03625-132">Il tipo fornito deve essere un tipo di riferimento di .NET.</span><span class="sxs-lookup"><span data-stu-id="03625-132">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="03625-133">Vincolo di tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="03625-133">Enumeration Type Constraint</span></span>|<span data-ttu-id="03625-134">: enumerazione&lt;*tipo sottostante*&gt;</span><span class="sxs-lookup"><span data-stu-id="03625-134">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="03625-135">Il tipo fornito deve essere un tipo enumerato che ha il tipo sottostante specificato. non può essere usata più comune.</span><span class="sxs-lookup"><span data-stu-id="03625-135">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="03625-136">Vincolo di delegato</span><span class="sxs-lookup"><span data-stu-id="03625-136">Delegate Constraint</span></span>|<span data-ttu-id="03625-137">: delegare&lt;*-tipo di parametro tupla*, *il tipo restituito*&gt;</span><span class="sxs-lookup"><span data-stu-id="03625-137">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="03625-138">Il tipo fornito deve essere un tipo delegato che contiene gli argomenti specificati e restituire value; non può essere usata più comune.</span><span class="sxs-lookup"><span data-stu-id="03625-138">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="03625-139">Vincolo di confronto</span><span class="sxs-lookup"><span data-stu-id="03625-139">Comparison Constraint</span></span>|<span data-ttu-id="03625-140">: confronto</span><span class="sxs-lookup"><span data-stu-id="03625-140">: comparison</span></span>|<span data-ttu-id="03625-141">Il tipo fornito deve supportare il confronto.</span><span class="sxs-lookup"><span data-stu-id="03625-141">The provided type must support comparison.</span></span>|
|<span data-ttu-id="03625-142">Vincolo di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="03625-142">Equality Constraint</span></span>|<span data-ttu-id="03625-143">: uguaglianza</span><span class="sxs-lookup"><span data-stu-id="03625-143">: equality</span></span>|<span data-ttu-id="03625-144">Il tipo fornito deve supportare l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="03625-144">The provided type must support equality.</span></span>|
|<span data-ttu-id="03625-145">Vincolo non gestito</span><span class="sxs-lookup"><span data-stu-id="03625-145">Unmanaged Constraint</span></span>|<span data-ttu-id="03625-146">: non gestito</span><span class="sxs-lookup"><span data-stu-id="03625-146">: unmanaged</span></span>|<span data-ttu-id="03625-147">Il tipo fornito deve essere un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="03625-147">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="03625-148">Tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), i tipi di enumerazione, `nativeptr&lt;_&gt;`, o una struttura non generica i cui campi sono tutti i tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="03625-148">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="03625-149">È necessario aggiungere un vincolo, se il codice deve usare una funzionalità che è disponibile per il tipo di vincolo ma non nei tipi in generale.</span><span class="sxs-lookup"><span data-stu-id="03625-149">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="03625-150">Ad esempio, se si utilizza il vincolo di tipo per specificare un tipo di classe, è possibile utilizzare uno dei metodi della classe della funzione generica o di un tipo.</span><span class="sxs-lookup"><span data-stu-id="03625-150">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="03625-151">Vincoli è talvolta necessario specificare durante la scrittura di parametri di tipo in modo esplicito, poiché senza un vincolo, il compilatore non ha modo di verificare che le funzionalità che si siano utilizzando saranno disponibili in qualsiasi tipo che può essere fornito in fase di esecuzione per il tipo parametro.</span><span class="sxs-lookup"><span data-stu-id="03625-151">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="03625-152">I vincoli di più comuni che è utilizzare nel codice F # sono vincoli di tipo specificare classi base o interfacce.</span><span class="sxs-lookup"><span data-stu-id="03625-152">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="03625-153">Gli altri vincoli vengono utilizzati dalla libreria F # per implementare determinate funzionalità, ad esempio il vincolo di membro esplicito, che viene utilizzato per implementare l'operatore di overload di operatori aritmetici o viene fornito principalmente perché F # supporta il completamento set di vincoli supportati da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="03625-153">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="03625-154">Durante il processo di inferenza del tipo, alcuni vincoli vengono automaticamente dedotti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="03625-154">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="03625-155">Ad esempio, se si utilizza il `+` operatore in una funzione, il compilatore deduce un vincolo di membro esplicito per i tipi di variabili utilizzate nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="03625-155">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="03625-156">Il codice seguente vengono illustrate alcune dichiarazioni di vincolo.</span><span class="sxs-lookup"><span data-stu-id="03625-156">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="03625-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03625-157">See Also</span></span>
[<span data-ttu-id="03625-158">Generics</span><span class="sxs-lookup"><span data-stu-id="03625-158">Generics</span></span>](index.md)

[<span data-ttu-id="03625-159">Vincoli</span><span class="sxs-lookup"><span data-stu-id="03625-159">Constraints</span></span>](constraints.md)
