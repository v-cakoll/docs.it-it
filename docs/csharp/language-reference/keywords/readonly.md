---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 66a096e8831f72a2216e8ba5dd9866046504624f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368621"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="27285-102">readonly (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="27285-102">readonly (C# Reference)</span></span>

<span data-ttu-id="27285-103">La `readonly` parola chiave è un modificatore che può essere usato in quattro contesti:</span><span class="sxs-lookup"><span data-stu-id="27285-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="27285-104">In una [dichiarazione](#readonly-field-example)di campo `readonly` indica che l'assegnazione al campo può essere eseguita solo come parte della dichiarazione o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="27285-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="27285-105">Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="27285-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="27285-106">`readonly`Non è possibile assegnare un campo dopo la chiusura del costruttore.</span><span class="sxs-lookup"><span data-stu-id="27285-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="27285-107">Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:</span><span class="sxs-lookup"><span data-stu-id="27285-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="27285-108">Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="27285-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="27285-109">Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto,</span><span class="sxs-lookup"><span data-stu-id="27285-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="27285-110">L'oggetto non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="27285-110">That object isn't immutable.</span></span> <span data-ttu-id="27285-111">Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="27285-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="27285-112">Tuttavia, il modificatore non impedisce la modifica dei dati dell'istanza del campo tramite il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="27285-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="27285-113">Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può generare un avviso [CA2104](/visualstudio/code-quality/ca2104) : "non dichiarare tipi di riferimento modificabili in sola lettura".</span><span class="sxs-lookup"><span data-stu-id="27285-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="27285-114">In una `readonly struct` definizione di tipo, `readonly` indica che il tipo di struttura non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="27285-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="27285-115">Per altre informazioni, vedere la sezione [ `readonly` struct](../builtin-types/struct.md#readonly-struct) dell'articolo [tipi di struttura](../builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="27285-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="27285-116">In una dichiarazione di membro di istanza all'interno di un tipo di struttura, `readonly` indica che un membro di istanza non modifica lo stato della struttura.</span><span class="sxs-lookup"><span data-stu-id="27285-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="27285-117">Per ulteriori informazioni, vedere la sezione [ `readonly` membri di istanza](../builtin-types/struct.md#readonly-instance-members) dell'articolo [tipi di struttura](../builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="27285-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="27285-118">In un [ `ref readonly` metodo restituito](#ref-readonly-return-example), il `readonly` modificatore indica che il metodo restituisce un riferimento e le Scritture non sono consentite a tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="27285-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="27285-119">I `readonly struct` `ref readonly` contesti e sono stati aggiunti in C# 7,2.</span><span class="sxs-lookup"><span data-stu-id="27285-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="27285-120">`readonly`membri struct aggiunti in C# 8,0</span><span class="sxs-lookup"><span data-stu-id="27285-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="27285-121">Esempio di campo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="27285-121">Readonly field example</span></span>

<span data-ttu-id="27285-122">In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear` , anche se viene assegnato un valore nel costruttore della classe:</span><span class="sxs-lookup"><span data-stu-id="27285-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="27285-123">È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27285-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="27285-124">Quando la variabile viene inizializzata nella dichiarazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="27285-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="27285-125">In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="27285-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="27285-126">Nel costruttore statico della classe che contiene la dichiarazione del campo statico.</span><span class="sxs-lookup"><span data-stu-id="27285-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="27285-127">Questi contesti del costruttore sono anche gli unici contesti in cui è possibile passare un `readonly` campo come parametro [out](out-parameter-modifier.md) o [ref](ref.md) .</span><span class="sxs-lookup"><span data-stu-id="27285-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="27285-128">La parola chiave `readonly` è diversa dalla parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="27285-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="27285-129">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="27285-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="27285-130">Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore.</span><span class="sxs-lookup"><span data-stu-id="27285-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="27285-131">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="27285-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="27285-132">Inoltre, mentre un `const` campo è una costante in fase di compilazione, il `readonly` campo può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="27285-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="27285-133">Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="27285-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="27285-134">verrà ricevuto il messaggio di errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="27285-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="27285-135">**Non è possibile assegnare un campo di sola lettura a (tranne che in un costruttore o in un inizializzatore di variabile)**</span><span class="sxs-lookup"><span data-stu-id="27285-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="27285-136">Esempio di restituzione riferimento di sola lettura</span><span class="sxs-lookup"><span data-stu-id="27285-136">Ref readonly return example</span></span>

<span data-ttu-id="27285-137">Il `readonly` modificatore di un oggetto `ref return` indica che il riferimento restituito non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="27285-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="27285-138">L'esempio seguente restituisce un riferimento all'origine.</span><span class="sxs-lookup"><span data-stu-id="27285-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="27285-139">Usa il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:</span><span class="sxs-lookup"><span data-stu-id="27285-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="27285-140">Il tipo restituito può non essere `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="27285-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="27285-141">Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="27285-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="27285-142">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="27285-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="27285-143">È anche possibile visualizzare le proposte specifiche del linguaggio:</span><span class="sxs-lookup"><span data-stu-id="27285-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="27285-144">struct Ref e ReadOnly struct</span><span class="sxs-lookup"><span data-stu-id="27285-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="27285-145">membri struct di sola lettura</span><span class="sxs-lookup"><span data-stu-id="27285-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="27285-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27285-146">See also</span></span>

- [<span data-ttu-id="27285-147">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="27285-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27285-148">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="27285-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="27285-149">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="27285-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="27285-150">Modificatori</span><span class="sxs-lookup"><span data-stu-id="27285-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="27285-151">const</span><span class="sxs-lookup"><span data-stu-id="27285-151">const</span></span>](const.md)
- [<span data-ttu-id="27285-152">Fields</span><span class="sxs-lookup"><span data-stu-id="27285-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
