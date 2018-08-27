---
title: Parola chiave class (Riferimenti per C#)
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: ea1e2e049a692fb9d86731c8a450b568f275f9a9
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924798"
---
# <a name="class-c-reference"></a><span data-ttu-id="b9b20-102">class (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b9b20-102">class (C# Reference)</span></span>

<span data-ttu-id="b9b20-103">Le classi vengono dichiarate usando la parola chiave `class`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b9b20-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="b9b20-104">Note</span><span class="sxs-lookup"><span data-stu-id="b9b20-104">Remarks</span></span>

<span data-ttu-id="b9b20-105">In C# è consentita solo l'eredità singola.</span><span class="sxs-lookup"><span data-stu-id="b9b20-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="b9b20-106">In altre parole, una classe può ereditare l'implementazione solo da una classe di base singola.</span><span class="sxs-lookup"><span data-stu-id="b9b20-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="b9b20-107">Una classe può tuttavia implementare più di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b9b20-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="b9b20-108">La tabella seguente illustra esempi di ereditarietà di classi e di implementazione di interfacce:</span><span class="sxs-lookup"><span data-stu-id="b9b20-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="b9b20-109">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="b9b20-109">Inheritance</span></span>|<span data-ttu-id="b9b20-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9b20-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="b9b20-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="b9b20-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="b9b20-112">Single</span><span class="sxs-lookup"><span data-stu-id="b9b20-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="b9b20-113">Nessuna, implementa due interfacce</span><span class="sxs-lookup"><span data-stu-id="b9b20-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="b9b20-114">Singola, implementa una sola interfaccia</span><span class="sxs-lookup"><span data-stu-id="b9b20-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="b9b20-115">Una classe dichiarata direttamente all'interno di uno spazio dei nomi, non annidata all'interno di altre classi, può essere [public](../../../csharp/language-reference/keywords/public.md) o [internal](../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="b9b20-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](../../../csharp/language-reference/keywords/public.md) or [internal](../../../csharp/language-reference/keywords/internal.md).</span></span> <span data-ttu-id="b9b20-116">Le classi sono `internal` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9b20-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="b9b20-117">I membri delle classi, incluse le classi annidate, possono essere [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md) o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-117">Class members, including nested classes, can be [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md), or `private protected`.</span></span> <span data-ttu-id="b9b20-118">I membri sono [private](../../../csharp/language-reference/keywords/private.md) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9b20-118">Members are [private](../../../csharp/language-reference/keywords/private.md) by default.</span></span>

<span data-ttu-id="b9b20-119">Per altre informazioni, vedere [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) (Modificatori di accesso).</span><span class="sxs-lookup"><span data-stu-id="b9b20-119">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="b9b20-120">È possibile dichiarare classi generiche che hanno parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="b9b20-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="b9b20-121">Per altre informazioni, vedere [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) (Classi generiche).</span><span class="sxs-lookup"><span data-stu-id="b9b20-121">For more information, see [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="b9b20-122">Una classe può contenere dichiarazioni dei membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9b20-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="b9b20-123">Costruttori</span><span class="sxs-lookup"><span data-stu-id="b9b20-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="b9b20-124">Costanti</span><span class="sxs-lookup"><span data-stu-id="b9b20-124">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="b9b20-125">Campi</span><span class="sxs-lookup"><span data-stu-id="b9b20-125">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="b9b20-126">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="b9b20-126">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="b9b20-127">Metodi</span><span class="sxs-lookup"><span data-stu-id="b9b20-127">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="b9b20-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b9b20-128">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="b9b20-129">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="b9b20-129">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)

- [<span data-ttu-id="b9b20-130">Operatori</span><span class="sxs-lookup"><span data-stu-id="b9b20-130">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [<span data-ttu-id="b9b20-131">Eventi</span><span class="sxs-lookup"><span data-stu-id="b9b20-131">Events</span></span>](../../../csharp/programming-guide/events/index.md)

- [<span data-ttu-id="b9b20-132">Delegati</span><span class="sxs-lookup"><span data-stu-id="b9b20-132">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="b9b20-133">Classi</span><span class="sxs-lookup"><span data-stu-id="b9b20-133">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="b9b20-134">Interfacce</span><span class="sxs-lookup"><span data-stu-id="b9b20-134">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

- [<span data-ttu-id="b9b20-135">Struct</span><span class="sxs-lookup"><span data-stu-id="b9b20-135">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

- [<span data-ttu-id="b9b20-136">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b9b20-136">Enumerations</span></span>](../../../csharp/programming-guide/enumeration-types.md)

## <a name="example"></a><span data-ttu-id="b9b20-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9b20-137">Example</span></span>

<span data-ttu-id="b9b20-138">L'esempio seguente illustra la dichiarazione di campi di classe, costruttori e metodi.</span><span class="sxs-lookup"><span data-stu-id="b9b20-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="b9b20-139">Illustra anche la creazione di istanze di oggetti e la stampa dei dati di istanza.</span><span class="sxs-lookup"><span data-stu-id="b9b20-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="b9b20-140">In questo esempio vengono dichiarate due classi.</span><span class="sxs-lookup"><span data-stu-id="b9b20-140">In this example, two classes are declared.</span></span> <span data-ttu-id="b9b20-141">La prima classe `Child`, contiene due campi privati (`name` e `age`), due costruttori pubblici e un metodo pubblico.</span><span class="sxs-lookup"><span data-stu-id="b9b20-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="b9b20-142">La seconda classe, `StringTest`, viene usata per contenere `Main`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="b9b20-143">Commenti</span><span class="sxs-lookup"><span data-stu-id="b9b20-143">Comments</span></span>

<span data-ttu-id="b9b20-144">Si noti che, nell'esempio precedente, i campi privati (`name` e `age`) sono accessibili solo tramite i metodi pubblici della classe `Child`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="b9b20-145">Ad esempio, non è possibile stampare il nome del figlio, dal metodo `Main`, usando un'istruzione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b9b20-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="b9b20-146">L'accesso ai membri private di `Child` da `Main` sarebbe possibile solo se `Main` fosse un membro della classe.</span><span class="sxs-lookup"><span data-stu-id="b9b20-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="b9b20-147">I tipi dichiarati all'interno di una classe senza un modificatore di accesso vengono impostati automaticamente a `private`; in tal modo i membri dei dati in questo esempio sarebbero sempre `private`, anche se la parola chiave venisse rimossa.</span><span class="sxs-lookup"><span data-stu-id="b9b20-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="b9b20-148">Infine, si noti che per l'oggetto creato usando il costruttore predefinito (`child3`), il campo age (età) è stato inizializzato su zero per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9b20-148">Finally, notice that for the object created using the default constructor (`child3`), the age field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b9b20-149">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b9b20-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b9b20-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9b20-150">See also</span></span>

[<span data-ttu-id="b9b20-151">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b9b20-151">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="b9b20-152">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b9b20-152">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="b9b20-153">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b9b20-153">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="b9b20-154">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="b9b20-154">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
