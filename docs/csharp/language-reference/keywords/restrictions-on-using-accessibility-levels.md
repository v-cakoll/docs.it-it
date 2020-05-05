---
title: Restrizioni relative all'uso dei livelli di accessibilità - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 8082dbd7398b6634b68f1dd2887cd55d6798a5d9
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795157"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="c2c18-102">Restrizioni relative all'uso dei livelli di accessibilità (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c2c18-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="c2c18-103">Quando si specifica un tipo in una dichiarazione, verificare se il livello di accessibilità del tipo dipende dal livello di accessibilità di un membro o di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="c2c18-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="c2c18-104">Ad esempio, la classe di base diretta deve essere accessibile almeno quanto la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c2c18-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="c2c18-105">Le dichiarazioni seguenti causano un errore del compilatore perché la classe di base `BaseClass` è meno accessibile di `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="c2c18-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="c2c18-106">Nella tabella seguente sono riepilogate le restrizioni relative ai livelli di accessibilità dichiarata.</span><span class="sxs-lookup"><span data-stu-id="c2c18-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="c2c18-107">Contesto</span><span class="sxs-lookup"><span data-stu-id="c2c18-107">Context</span></span>|<span data-ttu-id="c2c18-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c2c18-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="c2c18-109">Classi</span><span class="sxs-lookup"><span data-stu-id="c2c18-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="c2c18-110">La classe di base diretta di un tipo di classe deve essere accessibile almeno quanto il tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="c2c18-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="c2c18-111">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c2c18-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="c2c18-112">Le interfacce di base esplicite di un tipo di interfaccia devono essere accessibili almeno quanto il tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2c18-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="c2c18-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="c2c18-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="c2c18-114">Il tipo restituito e i tipi di parametro di un tipo delegato devono essere accessibili almeno quanto il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="c2c18-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="c2c18-115">Costanti</span><span class="sxs-lookup"><span data-stu-id="c2c18-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="c2c18-116">Il tipo di una costante deve essere accessibile almeno quanto la costante.</span><span class="sxs-lookup"><span data-stu-id="c2c18-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="c2c18-117">Fields</span><span class="sxs-lookup"><span data-stu-id="c2c18-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="c2c18-118">Il tipo di un campo deve essere accessibile almeno quanto il campo.</span><span class="sxs-lookup"><span data-stu-id="c2c18-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="c2c18-119">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2c18-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="c2c18-120">Il tipo restituito e i tipi di parametro di un metodo devono essere accessibili almeno quanto il metodo.</span><span class="sxs-lookup"><span data-stu-id="c2c18-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="c2c18-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c2c18-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="c2c18-122">Il tipo di una proprietà deve essere accessibile almeno quanto la proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2c18-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="c2c18-123">Events</span><span class="sxs-lookup"><span data-stu-id="c2c18-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="c2c18-124">Il tipo di un evento deve essere accessibile almeno quanto l'evento.</span><span class="sxs-lookup"><span data-stu-id="c2c18-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="c2c18-125">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="c2c18-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="c2c18-126">Il tipo e i tipi di parametro di un indicizzatore devono essere accessibili almeno quanto l'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="c2c18-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="c2c18-127">Operatori</span><span class="sxs-lookup"><span data-stu-id="c2c18-127">Operators</span></span>](../operators/index.md)|<span data-ttu-id="c2c18-128">Il tipo restituito e i tipi di parametro di un operatore devono essere accessibili almeno quanto l'operatore.</span><span class="sxs-lookup"><span data-stu-id="c2c18-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="c2c18-129">Costruttori</span><span class="sxs-lookup"><span data-stu-id="c2c18-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="c2c18-130">I tipi di parametro di un costruttore devono essere accessibili almeno quanto il costruttore.</span><span class="sxs-lookup"><span data-stu-id="c2c18-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="c2c18-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2c18-131">Example</span></span>

<span data-ttu-id="c2c18-132">L'esempio seguente contiene dichiarazioni errate di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="c2c18-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="c2c18-133">Il commento che segue ogni dichiarazione indica l'errore del compilatore previsto.</span><span class="sxs-lookup"><span data-stu-id="c2c18-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="c2c18-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c2c18-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2c18-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2c18-135">See also</span></span>

- [<span data-ttu-id="c2c18-136">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c2c18-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c2c18-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c2c18-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2c18-138">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c2c18-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2c18-139">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="c2c18-139">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c2c18-140">Dominio di accessibilità</span><span class="sxs-lookup"><span data-stu-id="c2c18-140">Accessibility Domain</span></span>](accessibility-domain.md)
- [<span data-ttu-id="c2c18-141">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="c2c18-141">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c2c18-142">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="c2c18-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="c2c18-143">pubblico</span><span class="sxs-lookup"><span data-stu-id="c2c18-143">public</span></span>](public.md)
- [<span data-ttu-id="c2c18-144">privata</span><span class="sxs-lookup"><span data-stu-id="c2c18-144">private</span></span>](private.md)
- [<span data-ttu-id="c2c18-145">protetto</span><span class="sxs-lookup"><span data-stu-id="c2c18-145">protected</span></span>](protected.md)
- [<span data-ttu-id="c2c18-146">internal</span><span class="sxs-lookup"><span data-stu-id="c2c18-146">internal</span></span>](internal.md)
