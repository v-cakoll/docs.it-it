---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 03/26/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 344d5e54fcd500e283c52fa7953c6366823f13f0
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345144"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="87b6e-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="87b6e-102">readonly (C# Reference)</span></span>

<span data-ttu-id="87b6e-103">La `readonly` parola chiave è un modificatore che può essere utilizzato in quattro contesti:The keyword is a modifier that can be used in four contexts:</span><span class="sxs-lookup"><span data-stu-id="87b6e-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="87b6e-104">In una [dichiarazione](#readonly-field-example)di campo , `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione o in un costruttore nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="87b6e-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="87b6e-105">Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="87b6e-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="87b6e-106">Un `readonly` campo non può essere assegnato dopo la chiusura del costruttore.</span><span class="sxs-lookup"><span data-stu-id="87b6e-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="87b6e-107">Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:This rule has different implications for value types and reference types:</span><span class="sxs-lookup"><span data-stu-id="87b6e-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="87b6e-108">Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="87b6e-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="87b6e-109">Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto,</span><span class="sxs-lookup"><span data-stu-id="87b6e-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="87b6e-110">Quell'oggetto non è immutabile.</span><span class="sxs-lookup"><span data-stu-id="87b6e-110">That object isn't immutable.</span></span> <span data-ttu-id="87b6e-111">Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="87b6e-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="87b6e-112">Tuttavia, il modificatore non impedisce la modifica dei dati di istanza del campo tramite il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="87b6e-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="87b6e-113">Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può attivare l'avviso [CA2104:](/visualstudio/code-quality/ca2104) "Non dichiarare tipi di riferimento modificabili di sola lettura".</span><span class="sxs-lookup"><span data-stu-id="87b6e-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="87b6e-114">In `readonly struct` una definizione di tipo indica `readonly` che il tipo di struttura non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="87b6e-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="87b6e-115">Per altre informazioni, [ `readonly` ](../builtin-types/struct.md#readonly-struct) vedere la sezione struct dell'articolo [Tipi di struttura.](../builtin-types/struct.md)</span><span class="sxs-lookup"><span data-stu-id="87b6e-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="87b6e-116">In una `readonly` `struct` [ `readonly` definizione](#readonly-member-examples)di membro , indica che un membro di un oggetto non modifica lo stato interno dello struct.</span><span class="sxs-lookup"><span data-stu-id="87b6e-116">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="87b6e-117">In [ `ref readonly` ](#ref-readonly-return-example)un metodo `readonly` restituito , il modificatore indica che il metodo restituisce un riferimento e le scritture non sono consentite a tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="87b6e-117">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="87b6e-118">I `readonly struct` `ref readonly` contesti e sono stati aggiunti in C .</span><span class="sxs-lookup"><span data-stu-id="87b6e-118">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="87b6e-119">`readonly`i membri di struct sono stati aggiunti in C</span><span class="sxs-lookup"><span data-stu-id="87b6e-119">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="87b6e-120">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="87b6e-120">Readonly field example</span></span>

<span data-ttu-id="87b6e-121">In questo esempio, il `year` valore del campo non `ChangeYear`può essere modificato nel metodo , anche se gli è stato assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="87b6e-121">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="87b6e-122">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="87b6e-122">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="87b6e-123">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87b6e-123">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="87b6e-124">In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="87b6e-124">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="87b6e-125">Nel costruttore statico della classe che contiene la dichiarazione del campo statico.</span><span class="sxs-lookup"><span data-stu-id="87b6e-125">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="87b6e-126">Questi contesti costruttore sono anche gli unici contesti `readonly` in cui è valido passare un campo come parametro [out](out-parameter-modifier.md) o [ref.](ref.md)</span><span class="sxs-lookup"><span data-stu-id="87b6e-126">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="87b6e-127">La parola chiave `readonly` è diversa dalla parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="87b6e-127">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="87b6e-128">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="87b6e-128">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="87b6e-129">Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore.</span><span class="sxs-lookup"><span data-stu-id="87b6e-129">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="87b6e-130">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="87b6e-130">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="87b6e-131">Inoltre, mentre `const` un campo è una `readonly` costante in fase di compilazione, il campo può essere utilizzato per le costanti in fase di esecuzione, come nell'esempio seguente:Also, while a field is a compile-time constant, the field can be used for run-time constants as in the following example:</span><span class="sxs-lookup"><span data-stu-id="87b6e-131">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="87b6e-132">Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="87b6e-132">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="87b6e-133">verrà visualizzato il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="87b6e-133">you'll get the compiler error message:</span></span>

<span data-ttu-id="87b6e-134">**Un campo readonly non può essere assegnato a (tranne in un costruttore o un inizializzatore di variabile)**</span><span class="sxs-lookup"><span data-stu-id="87b6e-134">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="87b6e-135">Esempi di membri di sola letturaReadonly member examples</span><span class="sxs-lookup"><span data-stu-id="87b6e-135">Readonly member examples</span></span>

<span data-ttu-id="87b6e-136">Altre volte, è possibile creare uno struct che supporta la mutazione.</span><span class="sxs-lookup"><span data-stu-id="87b6e-136">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="87b6e-137">In questi casi, è probabile che molti membri di istanza non modifichino lo stato interno dello struct.</span><span class="sxs-lookup"><span data-stu-id="87b6e-137">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="87b6e-138">È possibile dichiarare tali `readonly` membri di istanza con il modificatore .</span><span class="sxs-lookup"><span data-stu-id="87b6e-138">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="87b6e-139">Il compilatore applica l'intento.</span><span class="sxs-lookup"><span data-stu-id="87b6e-139">The compiler enforces your intent.</span></span> <span data-ttu-id="87b6e-140">Se tale membro modifica lo stato direttamente o accede a un membro `readonly` che non è dichiarato anche con il modificatore, il risultato è un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="87b6e-140">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="87b6e-141">Il `readonly` modificatore `struct` è valido `class` `interface` per i membri, non o le dichiarazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="87b6e-141">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="87b6e-142">È possibile ottenere due `readonly` vantaggi applicando `struct` il modificatore ai metodi applicabili.</span><span class="sxs-lookup"><span data-stu-id="87b6e-142">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="87b6e-143">Ancora più importante, il compilatore applica l'intento.</span><span class="sxs-lookup"><span data-stu-id="87b6e-143">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="87b6e-144">Il codice che modifica lo stato non `readonly` è valido in un metodo.</span><span class="sxs-lookup"><span data-stu-id="87b6e-144">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="87b6e-145">Il compilatore può anche `readonly` utilizzare il modificatore per abilitare le ottimizzazioni delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="87b6e-145">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="87b6e-146">Quando `struct` i tipi `in` di grandi dimensioni vengono passati per riferimento, il compilatore deve generare una copia difensiva se lo stato dello struct potrebbe essere modificato.</span><span class="sxs-lookup"><span data-stu-id="87b6e-146">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="87b6e-147">Se `readonly` si accede solo ai membri, il compilatore non può creare la copia difensiva.</span><span class="sxs-lookup"><span data-stu-id="87b6e-147">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="87b6e-148">Il `readonly` modificatore è valido `struct`nella maggior parte dei <xref:System.Object?displayProperty=nameWithType>membri di un oggetto , inclusi i metodi che eseguono l'override dei metodi dichiarati in .</span><span class="sxs-lookup"><span data-stu-id="87b6e-148">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87b6e-149">Ci sono alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="87b6e-149">There are some restrictions:</span></span>

- <span data-ttu-id="87b6e-150">Non è possibile `readonly` dichiarare proprietà o metodi statici.</span><span class="sxs-lookup"><span data-stu-id="87b6e-150">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="87b6e-151">Non è possibile `readonly` dichiarare costruttori.</span><span class="sxs-lookup"><span data-stu-id="87b6e-151">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="87b6e-152">È possibile `readonly` aggiungere il modificatore a una dichiarazione di proprietà o indicizzatore:You can add the modifier to a property or indexer declaration:</span><span class="sxs-lookup"><span data-stu-id="87b6e-152">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="87b6e-153">È inoltre possibile `readonly` aggiungere `get` il `set` modificatore a singole o funzioni di accesso di una proprietà o di un indicizzatore:You may also add the modifier to individual or accessors of a property or indexer:</span><span class="sxs-lookup"><span data-stu-id="87b6e-153">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="87b6e-154">Non è possibile `readonly` aggiungere il modificatore a una proprietà e a una o più funzioni di accesso della stessa proprietà.</span><span class="sxs-lookup"><span data-stu-id="87b6e-154">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="87b6e-155">La stessa restrizione si applica agli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="87b6e-155">That same restriction applies to indexers.</span></span>

<span data-ttu-id="87b6e-156">Il compilatore applica `readonly` in modo implicito il modificatore alle proprietà implementate automaticamente in cui il codice implementato dal compilatore non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="87b6e-156">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="87b6e-157">È equivalente alle seguenti dichiarazioni:</span><span class="sxs-lookup"><span data-stu-id="87b6e-157">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

<span data-ttu-id="87b6e-158">È possibile `readonly` aggiungere il modificatore in tali posizioni, ma non avrà alcun effetto significativo.</span><span class="sxs-lookup"><span data-stu-id="87b6e-158">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="87b6e-159">Non è possibile `readonly` aggiungere il modificatore a un setter di proprietà implementato automaticamente o a una proprietà implementata automaticamente di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="87b6e-159">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="87b6e-160">Esempio di restituzione riferimento di sola lettura</span><span class="sxs-lookup"><span data-stu-id="87b6e-160">Ref readonly return example</span></span>

<span data-ttu-id="87b6e-161">Il `readonly` modificatore `ref return` in un indica che il riferimento restituito non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="87b6e-161">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="87b6e-162">L'esempio seguente restituisce un riferimento all'origine.</span><span class="sxs-lookup"><span data-stu-id="87b6e-162">The following example returns a reference to the origin.</span></span> <span data-ttu-id="87b6e-163">Utilizza il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:</span><span class="sxs-lookup"><span data-stu-id="87b6e-163">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="87b6e-164">Il tipo restituito può non essere `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="87b6e-164">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="87b6e-165">Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="87b6e-165">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="87b6e-166">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="87b6e-166">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="87b6e-167">Puoi anche vedere le proposte di specifica del linguaggio:</span><span class="sxs-lookup"><span data-stu-id="87b6e-167">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="87b6e-168">readonly ref e struct readonly</span><span class="sxs-lookup"><span data-stu-id="87b6e-168">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="87b6e-169">membri struct readonlyReadonly struct members</span><span class="sxs-lookup"><span data-stu-id="87b6e-169">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="87b6e-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b6e-170">See also</span></span>

- [<span data-ttu-id="87b6e-171">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="87b6e-171">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="87b6e-172">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="87b6e-172">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="87b6e-173">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="87b6e-173">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="87b6e-174">Modificatori</span><span class="sxs-lookup"><span data-stu-id="87b6e-174">Modifiers</span></span>](index.md)
- [<span data-ttu-id="87b6e-175">const</span><span class="sxs-lookup"><span data-stu-id="87b6e-175">const</span></span>](const.md)
- [<span data-ttu-id="87b6e-176">Campi</span><span class="sxs-lookup"><span data-stu-id="87b6e-176">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
