---
title: Parola chiave class - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 61f15550482e8499e57197e35970e7ec8a096947
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345512"
---
# <a name="class-c-reference"></a><span data-ttu-id="f5677-102">class (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f5677-102">class (C# Reference)</span></span>

<span data-ttu-id="f5677-103">Le classi vengono dichiarate usando la parola chiave `class`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f5677-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="f5677-104">Note</span><span class="sxs-lookup"><span data-stu-id="f5677-104">Remarks</span></span>

<span data-ttu-id="f5677-105">In C# è consentita solo l'eredità singola.</span><span class="sxs-lookup"><span data-stu-id="f5677-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="f5677-106">In altre parole, una classe può ereditare l'implementazione solo da una classe di base singola.</span><span class="sxs-lookup"><span data-stu-id="f5677-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="f5677-107">Una classe può tuttavia implementare più di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f5677-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="f5677-108">La tabella seguente illustra esempi di ereditarietà di classi e di implementazione di interfacce:</span><span class="sxs-lookup"><span data-stu-id="f5677-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="f5677-109">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="f5677-109">Inheritance</span></span>|<span data-ttu-id="f5677-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5677-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="f5677-111">nessuna</span><span class="sxs-lookup"><span data-stu-id="f5677-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="f5677-112">Single</span><span class="sxs-lookup"><span data-stu-id="f5677-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="f5677-113">Nessuna, implementa due interfacce</span><span class="sxs-lookup"><span data-stu-id="f5677-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="f5677-114">Singola, implementa una sola interfaccia</span><span class="sxs-lookup"><span data-stu-id="f5677-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="f5677-115">Una classe dichiarata direttamente all'interno di uno spazio dei nomi, non annidata all'interno di altre classi, può essere [public](./public.md) o [internal](./internal.md).</span><span class="sxs-lookup"><span data-stu-id="f5677-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="f5677-116">Le classi sono `internal` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f5677-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="f5677-117">I membri di classe, incluse le classi annidate, possono essere [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) o [private protected](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="f5677-117">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="f5677-118">I membri sono `private` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f5677-118">Members are `private` by default.</span></span>

<span data-ttu-id="f5677-119">Per altre informazioni, vedere [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="f5677-119">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="f5677-120">È possibile dichiarare classi generiche che hanno parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="f5677-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="f5677-121">Per altre informazioni, vedere [Generic Classes](../../programming-guide/generics/generic-classes.md) (Classi generiche).</span><span class="sxs-lookup"><span data-stu-id="f5677-121">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="f5677-122">Una classe può contenere dichiarazioni dei membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5677-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="f5677-123">Costruttori</span><span class="sxs-lookup"><span data-stu-id="f5677-123">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="f5677-124">Costanti</span><span class="sxs-lookup"><span data-stu-id="f5677-124">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="f5677-125">Campi</span><span class="sxs-lookup"><span data-stu-id="f5677-125">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="f5677-126">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="f5677-126">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="f5677-127">Metodi</span><span class="sxs-lookup"><span data-stu-id="f5677-127">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="f5677-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f5677-128">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="f5677-129">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="f5677-129">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="f5677-130">Operatori</span><span class="sxs-lookup"><span data-stu-id="f5677-130">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="f5677-131">Eventi</span><span class="sxs-lookup"><span data-stu-id="f5677-131">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="f5677-132">Delegati</span><span class="sxs-lookup"><span data-stu-id="f5677-132">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="f5677-133">Classi</span><span class="sxs-lookup"><span data-stu-id="f5677-133">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="f5677-134">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f5677-134">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="f5677-135">Struct</span><span class="sxs-lookup"><span data-stu-id="f5677-135">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)

- [<span data-ttu-id="f5677-136">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="f5677-136">Enumerations</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="f5677-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5677-137">Example</span></span>

<span data-ttu-id="f5677-138">L'esempio seguente illustra la dichiarazione di campi di classe, costruttori e metodi.</span><span class="sxs-lookup"><span data-stu-id="f5677-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="f5677-139">Illustra anche la creazione di istanze di oggetti e la stampa dei dati di istanza.</span><span class="sxs-lookup"><span data-stu-id="f5677-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="f5677-140">In questo esempio vengono dichiarate due classi.</span><span class="sxs-lookup"><span data-stu-id="f5677-140">In this example, two classes are declared.</span></span> <span data-ttu-id="f5677-141">La prima classe `Child`, contiene due campi privati (`name` e `age`), due costruttori pubblici e un metodo pubblico.</span><span class="sxs-lookup"><span data-stu-id="f5677-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="f5677-142">La seconda classe, `StringTest`, viene usata per contenere `Main`.</span><span class="sxs-lookup"><span data-stu-id="f5677-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="f5677-143">Comments</span><span class="sxs-lookup"><span data-stu-id="f5677-143">Comments</span></span>

<span data-ttu-id="f5677-144">Si noti che, nell'esempio precedente, i campi privati (`name` e `age`) sono accessibili solo tramite i metodi pubblici della classe `Child`.</span><span class="sxs-lookup"><span data-stu-id="f5677-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="f5677-145">Ad esempio, non è possibile stampare il nome del figlio, dal metodo `Main`, usando un'istruzione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f5677-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="f5677-146">L'accesso ai membri private di `Child` da `Main` sarebbe possibile solo se `Main` fosse un membro della classe.</span><span class="sxs-lookup"><span data-stu-id="f5677-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="f5677-147">I tipi dichiarati all'interno di una classe senza un modificatore di accesso vengono impostati automaticamente a `private`; in tal modo i membri dei dati in questo esempio sarebbero sempre `private`, anche se la parola chiave venisse rimossa.</span><span class="sxs-lookup"><span data-stu-id="f5677-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="f5677-148">Infine, si noti che per l'oggetto creato usando il costruttore senza parametri (`child3`), il campo `age` è stato inizializzato su zero per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f5677-148">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f5677-149">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f5677-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f5677-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5677-150">See also</span></span>

- [<span data-ttu-id="f5677-151">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f5677-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f5677-152">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f5677-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f5677-153">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f5677-153">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="f5677-154">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="f5677-154">Reference Types</span></span>](./reference-types.md)
