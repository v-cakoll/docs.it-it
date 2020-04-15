---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 03b0aa63eda3e7a9d8745baaa33479fd5e85b01b
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389049"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="e2e6d-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e2e6d-102">readonly (C# Reference)</span></span>

<span data-ttu-id="e2e6d-103">La `readonly` parola chiave è un modificatore che può essere utilizzato in quattro contesti:The keyword is a modifier that can be used in four contexts:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="e2e6d-104">In una [dichiarazione](#readonly-field-example)di campo , `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione o in un costruttore nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="e2e6d-105">Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="e2e6d-106">Un `readonly` campo non può essere assegnato dopo la chiusura del costruttore.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="e2e6d-107">Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:This rule has different implications for value types and reference types:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="e2e6d-108">Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="e2e6d-109">Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto,</span><span class="sxs-lookup"><span data-stu-id="e2e6d-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="e2e6d-110">Quell'oggetto non è immutabile.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-110">That object isn't immutable.</span></span> <span data-ttu-id="e2e6d-111">Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="e2e6d-112">Tuttavia, il modificatore non impedisce la modifica dei dati di istanza del campo tramite il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="e2e6d-113">Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può attivare l'avviso [CA2104:](/visualstudio/code-quality/ca2104) "Non dichiarare tipi di riferimento modificabili di sola lettura".</span><span class="sxs-lookup"><span data-stu-id="e2e6d-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="e2e6d-114">In `readonly struct` una definizione di tipo indica `readonly` che il tipo di struttura non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="e2e6d-115">Per altre informazioni, [ `readonly` ](../builtin-types/struct.md#readonly-struct) vedere la sezione struct dell'articolo [Tipi di struttura.](../builtin-types/struct.md)</span><span class="sxs-lookup"><span data-stu-id="e2e6d-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="e2e6d-116">In una dichiarazione di membro `readonly` di istanza all'interno di un tipo di struttura, indica che un membro di istanza non modifica lo stato della struttura.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="e2e6d-117">Per altre informazioni, [ `readonly` ](../builtin-types/struct.md#readonly-instance-members) vedere la sezione dei membri di istanza dell'articolo [Tipi di struttura.](../builtin-types/struct.md)</span><span class="sxs-lookup"><span data-stu-id="e2e6d-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="e2e6d-118">In [ `ref readonly` ](#ref-readonly-return-example)un metodo `readonly` restituito , il modificatore indica che il metodo restituisce un riferimento e le scritture non sono consentite a tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="e2e6d-119">I `readonly struct` `ref readonly` contesti e sono stati aggiunti in C .</span><span class="sxs-lookup"><span data-stu-id="e2e6d-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="e2e6d-120">`readonly`i membri di struct sono stati aggiunti in C</span><span class="sxs-lookup"><span data-stu-id="e2e6d-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="e2e6d-121">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e2e6d-121">Readonly field example</span></span>

<span data-ttu-id="e2e6d-122">In questo esempio, il `year` valore del campo non `ChangeYear`può essere modificato nel metodo , anche se gli è stato assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="e2e6d-123">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="e2e6d-124">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="e2e6d-125">In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="e2e6d-126">Nel costruttore statico della classe che contiene la dichiarazione del campo statico.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="e2e6d-127">Questi contesti costruttore sono anche gli unici contesti `readonly` in cui è valido passare un campo come parametro [out](out-parameter-modifier.md) o [ref.](ref.md)</span><span class="sxs-lookup"><span data-stu-id="e2e6d-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="e2e6d-128">La parola chiave `readonly` è diversa dalla parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="e2e6d-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="e2e6d-129">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="e2e6d-130">Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="e2e6d-131">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="e2e6d-132">Inoltre, mentre `const` un campo è una `readonly` costante in fase di compilazione, il campo può essere utilizzato per le costanti in fase di esecuzione, come nell'esempio seguente:Also, while a field is a compile-time constant, the field can be used for run-time constants as in the following example:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="e2e6d-133">Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="e2e6d-134">verrà visualizzato il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="e2e6d-135">**Un campo readonly non può essere assegnato a (tranne in un costruttore o un inizializzatore di variabile)**</span><span class="sxs-lookup"><span data-stu-id="e2e6d-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="e2e6d-136">Esempio di restituzione riferimento di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e2e6d-136">Ref readonly return example</span></span>

<span data-ttu-id="e2e6d-137">Il `readonly` modificatore `ref return` in un indica che il riferimento restituito non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="e2e6d-138">L'esempio seguente restituisce un riferimento all'origine.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="e2e6d-139">Utilizza il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="e2e6d-140">Il tipo restituito può non essere `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="e2e6d-141">Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="e2e6d-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e2e6d-142">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e2e6d-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="e2e6d-143">Puoi anche vedere le proposte di specifica del linguaggio:</span><span class="sxs-lookup"><span data-stu-id="e2e6d-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="e2e6d-144">readonly ref e struct readonly</span><span class="sxs-lookup"><span data-stu-id="e2e6d-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="e2e6d-145">membri struct readonlyReadonly struct members</span><span class="sxs-lookup"><span data-stu-id="e2e6d-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="e2e6d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e6d-146">See also</span></span>

- [<span data-ttu-id="e2e6d-147">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e2e6d-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e2e6d-148">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="e2e6d-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e2e6d-149">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="e2e6d-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e2e6d-150">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e2e6d-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e2e6d-151">const</span><span class="sxs-lookup"><span data-stu-id="e2e6d-151">const</span></span>](const.md)
- [<span data-ttu-id="e2e6d-152">Fields</span><span class="sxs-lookup"><span data-stu-id="e2e6d-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
