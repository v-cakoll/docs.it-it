---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: c3db8f7791e510768608e834339526fb82771979
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451941"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="5c26b-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5c26b-102">readonly (C# Reference)</span></span>

<span data-ttu-id="5c26b-103">La parola chiave `readonly` è un modificatore che può essere usata in quattro contesti:</span><span class="sxs-lookup"><span data-stu-id="5c26b-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="5c26b-104">In una [dichiarazione di campo](#readonly-field-example)`readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione del campo o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="5c26b-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="5c26b-105">Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c26b-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="5c26b-106">Non è possibile assegnare un campo `readonly` dopo la chiusura del costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c26b-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="5c26b-107">Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="5c26b-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="5c26b-108">Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="5c26b-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="5c26b-109">Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto,</span><span class="sxs-lookup"><span data-stu-id="5c26b-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="5c26b-110">L'oggetto non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="5c26b-110">That object isn't immutable.</span></span> <span data-ttu-id="5c26b-111">Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5c26b-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="5c26b-112">Tuttavia, il modificatore non impedisce la modifica dei dati dell'istanza del campo tramite il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5c26b-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="5c26b-113">Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può generare un avviso [CA2104](/visualstudio/code-quality/ca2104) : "non dichiarare tipi di riferimento modificabili in sola lettura".</span><span class="sxs-lookup"><span data-stu-id="5c26b-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="5c26b-114">In una definizione [`readonly struct`](#readonly-struct-example), `readonly` indica che non è possibile modificare `struct`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="5c26b-115">In una [definizione di membro`readonly`](#readonly-member-examples)`readonly` indica che un membro di un `struct` non modifica lo stato interno dello struct.</span><span class="sxs-lookup"><span data-stu-id="5c26b-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="5c26b-116">In un [`ref readonly` metodo restituito](#ref-readonly-return-example), il modificatore di `readonly` indica che il metodo restituisce un riferimento e le Scritture non sono consentite a tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="5c26b-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="5c26b-117">I contesti di `readonly struct` e `ref readonly` sono stati C# aggiunti in 7,2.</span><span class="sxs-lookup"><span data-stu-id="5c26b-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="5c26b-118">`readonly` membri struct sono stati aggiunti C# in 8,0</span><span class="sxs-lookup"><span data-stu-id="5c26b-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="5c26b-119">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5c26b-119">Readonly field example</span></span>

<span data-ttu-id="5c26b-120">In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se viene assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="5c26b-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="5c26b-121">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c26b-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="5c26b-122">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5c26b-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="5c26b-123">In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="5c26b-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="5c26b-124">Nel costruttore statico della classe che contiene la dichiarazione del campo statico.</span><span class="sxs-lookup"><span data-stu-id="5c26b-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="5c26b-125">Questi contesti di costruttori sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](out-parameter-modifier.md) o [ref](ref.md) .</span><span class="sxs-lookup"><span data-stu-id="5c26b-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="5c26b-126">La parola chiave `readonly` è diversa dalla parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="5c26b-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="5c26b-127">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="5c26b-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="5c26b-128">Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c26b-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="5c26b-129">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="5c26b-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="5c26b-130">Inoltre, mentre un campo `const` è una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c26b-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="5c26b-131">Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c26b-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="5c26b-132">verrà ricevuto il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="5c26b-132">you'll get the compiler error message:</span></span>

<span data-ttu-id="5c26b-133">**Non è possibile assegnare un campo di sola lettura a (tranne che in un costruttore o in un inizializzatore di variabile)**</span><span class="sxs-lookup"><span data-stu-id="5c26b-133">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-struct-example"></a><span data-ttu-id="5c26b-134">Esempio di struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5c26b-134">Readonly struct example</span></span>

<span data-ttu-id="5c26b-135">Il modificatore `readonly` in una definizione `struct` dichiara che struct **non è modificabile**.</span><span class="sxs-lookup"><span data-stu-id="5c26b-135">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="5c26b-136">Tutti i campi di istanza di `struct` devono essere contrassegnati `readonly`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c26b-136">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="5c26b-137">Nell'esempio precedente vengono usate le [proprietà automatiche di sola lettura](../../properties.md#read-only) per dichiarare la risorsa di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5c26b-137">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="5c26b-138">Ciò indica al compilatore di creare campi sottostanti `readonly` per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c26b-138">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="5c26b-139">È inoltre possibile dichiarare i campi `readonly` direttamente:</span><span class="sxs-lookup"><span data-stu-id="5c26b-139">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="5c26b-140">L'aggiunta di un campo non contrassegnato `readonly` genera l'errore del compilatore `CS8340`: "Instance fields of readonly structs must be readonly" (I campi dell'istanza delle strutture di sola lettura devono essere di sola lettura).</span><span class="sxs-lookup"><span data-stu-id="5c26b-140">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="5c26b-141">Esempi di membri di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5c26b-141">Readonly member examples</span></span>

<span data-ttu-id="5c26b-142">In altri casi, è possibile creare uno struct che supporti la mutazione.</span><span class="sxs-lookup"><span data-stu-id="5c26b-142">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="5c26b-143">In questi casi, è probabile che molti membri di istanza non modifichino lo stato interno dello struct.</span><span class="sxs-lookup"><span data-stu-id="5c26b-143">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="5c26b-144">È possibile dichiarare i membri di istanza con il modificatore `readonly`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-144">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="5c26b-145">Il compilatore impone l'intento.</span><span class="sxs-lookup"><span data-stu-id="5c26b-145">The compiler enforces your intent.</span></span> <span data-ttu-id="5c26b-146">Se tale membro modifica lo stato direttamente o accede a un membro che non è dichiarato anche con il modificatore `readonly`, il risultato è un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5c26b-146">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="5c26b-147">Il modificatore `readonly` è valido nei membri `struct`, non `class` o `interface` dichiarazioni di membri.</span><span class="sxs-lookup"><span data-stu-id="5c26b-147">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="5c26b-148">Si ottengono due vantaggi applicando il modificatore `readonly` ai metodi `struct` applicabili.</span><span class="sxs-lookup"><span data-stu-id="5c26b-148">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="5c26b-149">In particolare, il compilatore impone l'intento.</span><span class="sxs-lookup"><span data-stu-id="5c26b-149">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="5c26b-150">Il codice che modifica lo stato non è valido in un metodo `readonly`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-150">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="5c26b-151">Il compilatore può inoltre utilizzare il modificatore `readonly` per abilitare le ottimizzazioni delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5c26b-151">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="5c26b-152">Quando i tipi di `struct` di grandi dimensioni vengono passati per riferimento `in`, il compilatore deve generare una copia difensiva se lo stato dello struct potrebbe essere modificato.</span><span class="sxs-lookup"><span data-stu-id="5c26b-152">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="5c26b-153">Se si accede solo ai membri `readonly`, il compilatore potrebbe non creare la copia difensiva.</span><span class="sxs-lookup"><span data-stu-id="5c26b-153">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="5c26b-154">Il modificatore `readonly` è valido per la maggior parte dei membri di un `struct`, inclusi i metodi che eseguono l'override dei metodi dichiarati in <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c26b-154">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c26b-155">Esistono alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="5c26b-155">There are some restrictions:</span></span>

- <span data-ttu-id="5c26b-156">Non è possibile dichiarare `readonly` metodi o proprietà statiche.</span><span class="sxs-lookup"><span data-stu-id="5c26b-156">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="5c26b-157">Non è possibile dichiarare `readonly` costruttori.</span><span class="sxs-lookup"><span data-stu-id="5c26b-157">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="5c26b-158">È possibile aggiungere il modificatore `readonly` a una dichiarazione di proprietà o di indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="5c26b-158">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="5c26b-159">È anche possibile aggiungere il modificatore `readonly` a singole `get` o `set` funzioni di accesso di una proprietà o di un indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="5c26b-159">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="5c26b-160">Non è possibile aggiungere il modificatore `readonly` sia a una proprietà che a una o più funzioni di accesso della stessa proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c26b-160">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="5c26b-161">Questa stessa restrizione si applica agli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="5c26b-161">That same restriction applies to indexers.</span></span>

<span data-ttu-id="5c26b-162">Il compilatore applica in modo implicito il modificatore `readonly` alle proprietà implementate automaticamente in cui il codice implementato dal compilatore non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="5c26b-162">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="5c26b-163">Equivale alle dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c26b-163">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

<span data-ttu-id="5c26b-164">È possibile aggiungere il modificatore `readonly` in tali percorsi, ma non avrà alcun effetto significativo.</span><span class="sxs-lookup"><span data-stu-id="5c26b-164">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="5c26b-165">Non è possibile aggiungere il modificatore `readonly` a un setter di proprietà implementato automaticamente o a una proprietà implementata automaticamente in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="5c26b-165">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="5c26b-166">Esempio di restituzione riferimento di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5c26b-166">Ref readonly return example</span></span>

<span data-ttu-id="5c26b-167">Il modificatore `readonly` in un `ref return` indica che non è possibile modificare il riferimento restituito.</span><span class="sxs-lookup"><span data-stu-id="5c26b-167">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="5c26b-168">L'esempio seguente restituisce un riferimento all'origine.</span><span class="sxs-lookup"><span data-stu-id="5c26b-168">The following example returns a reference to the origin.</span></span> <span data-ttu-id="5c26b-169">Usa il modificatore `readonly` per indicare che i chiamanti non possono modificare l'origine:</span><span class="sxs-lookup"><span data-stu-id="5c26b-169">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="5c26b-170">Il tipo restituito può non essere `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-170">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="5c26b-171">Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-171">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5c26b-172">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5c26b-172">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="5c26b-173">È anche possibile visualizzare le proposte specifiche del linguaggio:</span><span class="sxs-lookup"><span data-stu-id="5c26b-173">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="5c26b-174">struct Ref e ReadOnly struct</span><span class="sxs-lookup"><span data-stu-id="5c26b-174">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="5c26b-175">membri struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5c26b-175">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="5c26b-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c26b-176">See also</span></span>

- [<span data-ttu-id="5c26b-177">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5c26b-177">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5c26b-178">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5c26b-178">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5c26b-179">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="5c26b-179">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5c26b-180">Modificatori</span><span class="sxs-lookup"><span data-stu-id="5c26b-180">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5c26b-181">const</span><span class="sxs-lookup"><span data-stu-id="5c26b-181">const</span></span>](const.md)
- [<span data-ttu-id="5c26b-182">Campi</span><span class="sxs-lookup"><span data-stu-id="5c26b-182">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
