---
title: Parola chiave readonly - Riferimenti per C#
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348015"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="79042-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="79042-102">readonly (C# Reference)</span></span>

<span data-ttu-id="79042-103">La parola chiave `readonly` è un modificatore che può essere usato in tre contesti:</span><span class="sxs-lookup"><span data-stu-id="79042-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="79042-104">In una [dichiarazione di campo](#readonly-field-example) `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione del campo o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="79042-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="79042-105">Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="79042-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="79042-106">Un campo `readonly` non può essere assegnato dopo aver chiuso il costruttore.</span><span class="sxs-lookup"><span data-stu-id="79042-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="79042-107">Questo aspetto presenta implicazioni diverse per i tipi di valore e i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="79042-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="79042-108">Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="79042-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="79042-109">Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto,</span><span class="sxs-lookup"><span data-stu-id="79042-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="79042-110">che non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="79042-110">That object is not immutable.</span></span> <span data-ttu-id="79042-111">Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="79042-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="79042-112">Il modificatore non impedisce tuttavia che i dati dell'istanza vengano modificati mediante il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="79042-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="79042-113">Un tipo visibile esternamente contenente un campo di sola lettura visibile esternamente e costituito da un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può attivare l'avviso [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types): "Non dichiarare tipi di riferimento modificabili in sola lettura".</span><span class="sxs-lookup"><span data-stu-id="79042-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="79042-114">In una definizione [`readonly struct` ](#readonly-struct-example), `readonly` indica che non è possibile modificare `struct`.</span><span class="sxs-lookup"><span data-stu-id="79042-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="79042-115">In una restituzione del metodo[ `ref readonly`](#ref-readonly-return-example), il modificatore `readonly` indica che il metodo restituisce un riferimento e nel riferimento non sono consentite le scritture.</span><span class="sxs-lookup"><span data-stu-id="79042-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="79042-116">I due contesti finali sono stati aggiunti in C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="79042-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="79042-117">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="79042-117">Readonly field example</span></span>

<span data-ttu-id="79042-118">In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se gli viene assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="79042-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="79042-119">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="79042-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="79042-120">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79042-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="79042-121">In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="79042-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="79042-122">Nel costruttore statico della classe che contiene la dichiarazione del campo statico.</span><span class="sxs-lookup"><span data-stu-id="79042-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="79042-123">Questi contesti di costruttore sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](out-parameter-modifier.md) o [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="79042-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="79042-124">La parola chiave `readonly` è diversa dalla parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="79042-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="79042-125">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="79042-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="79042-126">Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore.</span><span class="sxs-lookup"><span data-stu-id="79042-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="79042-127">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="79042-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="79042-128">Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79042-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="79042-129">Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79042-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="79042-130">si otterrà il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="79042-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="79042-131">Esempio di struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="79042-131">Readonly struct example</span></span>

<span data-ttu-id="79042-132">Il modificatore `readonly` in una definizione `struct` dichiara che struct **non è modificabile**.</span><span class="sxs-lookup"><span data-stu-id="79042-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="79042-133">Tutti i campi di istanza di `struct` devono essere contrassegnati `readonly`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79042-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="79042-134">Nell'esempio precedente vengono usate le [proprietà automatiche di sola lettura](../../properties.md#read-only) per dichiarare la risorsa di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="79042-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="79042-135">Ciò indica al compilatore di creare campi sottostanti `readonly` per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="79042-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="79042-136">È inoltre possibile dichiarare i campi `readonly` direttamente:</span><span class="sxs-lookup"><span data-stu-id="79042-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="79042-137">L'aggiunta di un campo non contrassegnato come `readonly` genera l'errore del compilatore `CS8340`: "I campi di istanza di struct di sola lettura devono essere di sola lettura."</span><span class="sxs-lookup"><span data-stu-id="79042-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="79042-138">Esempio di restituzione riferimento di sola lettura</span><span class="sxs-lookup"><span data-stu-id="79042-138">Ref readonly return example</span></span>

<span data-ttu-id="79042-139">Il modificatore `readonly` in un `ref return` indica che il riferimento restituito non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="79042-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="79042-140">L'esempio seguente restituisce un riferimento all'origine.</span><span class="sxs-lookup"><span data-stu-id="79042-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="79042-141">Usa il modificatore `readonly` per indicare che i chiamanti non possono modificare l'origine:</span><span class="sxs-lookup"><span data-stu-id="79042-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="79042-142">Il tipo restituito può non essere `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="79042-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="79042-143">Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="79042-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="79042-144">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="79042-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="79042-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79042-145">See also</span></span>

- [<span data-ttu-id="79042-146">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="79042-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="79042-147">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="79042-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="79042-148">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="79042-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="79042-149">Modificatori</span><span class="sxs-lookup"><span data-stu-id="79042-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="79042-150">const</span><span class="sxs-lookup"><span data-stu-id="79042-150">const</span></span>](const.md)
- [<span data-ttu-id="79042-151">Campi</span><span class="sxs-lookup"><span data-stu-id="79042-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
