---
title: Vincoli
description: Informazioni sui F# vincoli che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.
ms.date: 05/16/2016
ms.openlocfilehash: 9912ba63138d893a7c616661dd2b1cbdbe51916c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736799"
---
# <a name="constraints"></a><span data-ttu-id="21ad2-103">Vincoli</span><span class="sxs-lookup"><span data-stu-id="21ad2-103">Constraints</span></span>

<span data-ttu-id="21ad2-104">In questo argomento vengono descritti i vincoli che è possibile applicare ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="21ad2-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="21ad2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21ad2-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="21ad2-106">Note</span><span class="sxs-lookup"><span data-stu-id="21ad2-106">Remarks</span></span>

<span data-ttu-id="21ad2-107">Esistono diversi vincoli che è possibile applicare per limitare i tipi che possono essere utilizzati in un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="21ad2-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="21ad2-108">La tabella seguente elenca e descrive questi vincoli.</span><span class="sxs-lookup"><span data-stu-id="21ad2-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="21ad2-109">Vincolo</span><span class="sxs-lookup"><span data-stu-id="21ad2-109">Constraint</span></span>|<span data-ttu-id="21ad2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21ad2-110">Syntax</span></span>|<span data-ttu-id="21ad2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21ad2-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="21ad2-112">Vincolo di tipo</span><span class="sxs-lookup"><span data-stu-id="21ad2-112">Type Constraint</span></span>|<span data-ttu-id="21ad2-113">*parametro Type* : *tipo* &gt;</span><span class="sxs-lookup"><span data-stu-id="21ad2-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="21ad2-114">Il tipo fornito deve essere uguale o derivato dal tipo specificato oppure, se il tipo è un'interfaccia, il tipo fornito deve implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="21ad2-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="21ad2-115">Vincolo null</span><span class="sxs-lookup"><span data-stu-id="21ad2-115">Null Constraint</span></span>|<span data-ttu-id="21ad2-116">*parametro di tipo* : null</span><span class="sxs-lookup"><span data-stu-id="21ad2-116">*type-parameter* : null</span></span>|<span data-ttu-id="21ad2-117">Il tipo specificato deve supportare il valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="21ad2-117">The provided type must support the null literal.</span></span> <span data-ttu-id="21ad2-118">Sono inclusi tutti i tipi di oggetto .NET F# , ma non i tipi List, Tuple, Function, Class, record o Union.</span><span class="sxs-lookup"><span data-stu-id="21ad2-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="21ad2-119">Vincolo membro esplicito</span><span class="sxs-lookup"><span data-stu-id="21ad2-119">Explicit Member Constraint</span></span>|<span data-ttu-id="21ad2-120">[(]*parametro di tipo* [or... o *parametro di tipo*)]: (*firma del membro*)</span><span class="sxs-lookup"><span data-stu-id="21ad2-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="21ad2-121">Almeno uno degli argomenti di tipo forniti deve avere un membro con la firma specificata. non è destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="21ad2-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="21ad2-122">I membri devono essere definiti in modo esplicito nel tipo o in una parte di un'estensione di tipo implicita come destinazioni valide per un vincolo di membro esplicito.</span><span class="sxs-lookup"><span data-stu-id="21ad2-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="21ad2-123">Vincolo del costruttore</span><span class="sxs-lookup"><span data-stu-id="21ad2-123">Constructor Constraint</span></span>|<span data-ttu-id="21ad2-124">*parametro di tipo* : (nuovo: unit-&gt;' a)</span><span class="sxs-lookup"><span data-stu-id="21ad2-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="21ad2-125">Il tipo specificato deve avere un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="21ad2-125">The provided type must have a parameterless constructor.</span></span>|
|<span data-ttu-id="21ad2-126">Vincolo di tipo valore</span><span class="sxs-lookup"><span data-stu-id="21ad2-126">Value Type Constraint</span></span>|<span data-ttu-id="21ad2-127">: struct</span><span class="sxs-lookup"><span data-stu-id="21ad2-127">: struct</span></span>|<span data-ttu-id="21ad2-128">Il tipo specificato deve essere un tipo di valore .NET.</span><span class="sxs-lookup"><span data-stu-id="21ad2-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="21ad2-129">Vincolo di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="21ad2-129">Reference Type Constraint</span></span>|<span data-ttu-id="21ad2-130">: not struct</span><span class="sxs-lookup"><span data-stu-id="21ad2-130">: not struct</span></span>|<span data-ttu-id="21ad2-131">Il tipo specificato deve essere un tipo di riferimento .NET.</span><span class="sxs-lookup"><span data-stu-id="21ad2-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="21ad2-132">Vincolo di tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="21ad2-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="21ad2-133">: enum @ no__t-0*sottostante-tipo*&gt;</span><span class="sxs-lookup"><span data-stu-id="21ad2-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="21ad2-134">Il tipo specificato deve essere un tipo enumerato con il tipo sottostante specificato. non è destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="21ad2-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="21ad2-135">Vincolo delegate</span><span class="sxs-lookup"><span data-stu-id="21ad2-135">Delegate Constraint</span></span>|<span data-ttu-id="21ad2-136">: Delegate @ no__t-0*Tuple-parameter-type*, *return-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="21ad2-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="21ad2-137">Il tipo specificato deve essere un tipo delegato con gli argomenti e il valore restituito specificati. non è destinato all'uso comune.</span><span class="sxs-lookup"><span data-stu-id="21ad2-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="21ad2-138">Vincolo di confronto</span><span class="sxs-lookup"><span data-stu-id="21ad2-138">Comparison Constraint</span></span>|<span data-ttu-id="21ad2-139">: confronto</span><span class="sxs-lookup"><span data-stu-id="21ad2-139">: comparison</span></span>|<span data-ttu-id="21ad2-140">Il tipo fornito deve supportare il confronto.</span><span class="sxs-lookup"><span data-stu-id="21ad2-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="21ad2-141">Vincolo di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="21ad2-141">Equality Constraint</span></span>|<span data-ttu-id="21ad2-142">: uguaglianza</span><span class="sxs-lookup"><span data-stu-id="21ad2-142">: equality</span></span>|<span data-ttu-id="21ad2-143">Il tipo specificato deve supportare l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="21ad2-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="21ad2-144">Vincolo non gestito</span><span class="sxs-lookup"><span data-stu-id="21ad2-144">Unmanaged Constraint</span></span>|<span data-ttu-id="21ad2-145">: non gestito</span><span class="sxs-lookup"><span data-stu-id="21ad2-145">: unmanaged</span></span>|<span data-ttu-id="21ad2-146">Il tipo specificato deve essere un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="21ad2-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="21ad2-147">I tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, 0, 1, 2 o 3), tipi di enumerazione, 4 o un oggetto non generico struttura i cui campi sono tutti tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="21ad2-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="21ad2-148">È necessario aggiungere un vincolo quando il codice deve usare una funzionalità disponibile sul tipo di vincolo ma non sui tipi in generale.</span><span class="sxs-lookup"><span data-stu-id="21ad2-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="21ad2-149">Se ad esempio si usa il vincolo di tipo per specificare un tipo di classe, è possibile usare uno dei metodi di tale classe nella funzione o nel tipo generico.</span><span class="sxs-lookup"><span data-stu-id="21ad2-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="21ad2-150">Quando si scrivono parametri di tipo in modo esplicito, è talvolta necessario specificare vincoli perché senza un vincolo il compilatore non è in grado di verificare che le funzionalità in uso siano disponibili in qualsiasi tipo che potrebbe essere fornito in fase di esecuzione per il tipo parametro.</span><span class="sxs-lookup"><span data-stu-id="21ad2-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="21ad2-151">I vincoli più comuni usati nel codice F# sono vincoli di tipo che specificano le classi o le interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="21ad2-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="21ad2-152">Gli altri vincoli vengono usati dalla F# libreria per implementare determinate funzionalità, ad esempio il vincolo esplicito dei membri, che viene usato per implementare l'overload degli operatori per gli operatori aritmetici o vengono forniti principalmente F# perché supporta il set completo di vincoli supportato dal Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="21ad2-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="21ad2-153">Durante il processo di inferenza del tipo, alcuni vincoli vengono dedotti automaticamente dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="21ad2-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="21ad2-154">Se, ad esempio, si usa l'operatore `+` in una funzione, il compilatore deduce un vincolo esplicito dei membri sui tipi di variabile usati nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="21ad2-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="21ad2-155">Il codice seguente illustra alcune dichiarazioni di vincolo:</span><span class="sxs-lookup"><span data-stu-id="21ad2-155">The following code illustrates some constraint declarations:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="21ad2-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21ad2-156">See also</span></span>

- [<span data-ttu-id="21ad2-157">Generics</span><span class="sxs-lookup"><span data-stu-id="21ad2-157">Generics</span></span>](index.md)
- [<span data-ttu-id="21ad2-158">Vincoli</span><span class="sxs-lookup"><span data-stu-id="21ad2-158">Constraints</span></span>](constraints.md)
