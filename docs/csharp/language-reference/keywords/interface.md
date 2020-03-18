---
title: interface - Riferimenti per C#
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625852"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="e01d0-102">:::no-loc text="interface":::(Riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="e01d0-102">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="e01d0-103">Un'interfaccia definisce un contratto.</span><span class="sxs-lookup"><span data-stu-id="e01d0-103">An interface defines a contract.</span></span> <span data-ttu-id="e01d0-104">Qualsiasi [`class`](class.md) [`struct`](../builtin-types/struct.md) o che implementa tale contratto deve fornire un'implementazione dei membri definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-104">Any [`class`](class.md) or [`struct`](../builtin-types/struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="e01d0-105">A partire dalla versione 8.0 di C, un'interfaccia può definire un'implementazione predefinita per i membri.</span><span class="sxs-lookup"><span data-stu-id="e01d0-105">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="e01d0-106">Può anche [`static`](static.md) definire membri per fornire una singola implementazione per le funzionalità comuni.</span><span class="sxs-lookup"><span data-stu-id="e01d0-106">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="e01d0-107">Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="e01d0-107">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="e01d0-108">Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="e01d0-108">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="e01d0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e01d0-109">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="e01d0-110">Un'interfaccia può essere un membro di uno spazio dei nomi o di una classe.</span><span class="sxs-lookup"><span data-stu-id="e01d0-110">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="e01d0-111">Una dichiarazione di interfaccia può contenere dichiarazioni (firme senza alcuna implementazione) dei membri seguenti:An interface declaration can contain declarations (signatures without any implementation) of the following members:</span><span class="sxs-lookup"><span data-stu-id="e01d0-111">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="e01d0-112">Metodi</span><span class="sxs-lookup"><span data-stu-id="e01d0-112">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="e01d0-113">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e01d0-113">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="e01d0-114">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="e01d0-114">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="e01d0-115">Events</span><span class="sxs-lookup"><span data-stu-id="e01d0-115">Events</span></span>](event.md)

<span data-ttu-id="e01d0-116">Queste dichiarazioni di membro precedenti in genere non contengono un corpo.</span><span class="sxs-lookup"><span data-stu-id="e01d0-116">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="e01d0-117">A partire dalla versione 8.0 di C, un membro di interfaccia può dichiarare un corpo.</span><span class="sxs-lookup"><span data-stu-id="e01d0-117">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="e01d0-118">Questa operazione è denominata *implementazione predefinita*.</span><span class="sxs-lookup"><span data-stu-id="e01d0-118">This is called a *default implementation*.</span></span> <span data-ttu-id="e01d0-119">I membri con corpi consentono all'interfaccia di fornire un'implementazione "predefinita" per classi e struct che non forniscono un'implementazione di override.</span><span class="sxs-lookup"><span data-stu-id="e01d0-119">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="e01d0-120">Inoltre, a partire da C , 8.0, un'interfaccia può includere:In addition, beginning with C's 8.0, an interface may include:</span><span class="sxs-lookup"><span data-stu-id="e01d0-120">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="e01d0-121">Costanti</span><span class="sxs-lookup"><span data-stu-id="e01d0-121">Constants</span></span>](const.md)
- [<span data-ttu-id="e01d0-122">Operatori</span><span class="sxs-lookup"><span data-stu-id="e01d0-122">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="e01d0-123">[Costruttore statico](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span><span class="sxs-lookup"><span data-stu-id="e01d0-123">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="e01d0-124">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="e01d0-124">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- [<span data-ttu-id="e01d0-125">Campi, metodi, proprietà, indicizzatori ed eventi statici</span><span class="sxs-lookup"><span data-stu-id="e01d0-125">Static fields, methods, properties, indexers, and events</span></span>](static.md)
- <span data-ttu-id="e01d0-126">Dichiarazioni di membri utilizzando la sintassi di implementazione esplicita dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-126">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="e01d0-127">Modificatori di accesso espliciti [`public`](access-modifiers.md)(l'accesso predefinito è ).</span><span class="sxs-lookup"><span data-stu-id="e01d0-127">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="e01d0-128">Le interfacce non possono contenere lo stato dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="e01d0-128">Interfaces may not contain instance state.</span></span> <span data-ttu-id="e01d0-129">Sebbene i campi statici siano ora consentiti, i campi di istanza non sono consentiti nelle interfacce.</span><span class="sxs-lookup"><span data-stu-id="e01d0-129">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="e01d0-130">[Le proprietà automatiche dell'istanza](../../programming-guide/classes-and-structs/auto-implemented-properties.md) non sono supportate nelle interfacce, in quanto dichiarano in modo implicito un campo nascosto.</span><span class="sxs-lookup"><span data-stu-id="e01d0-130">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="e01d0-131">Questa regola ha un effetto sottile sulle dichiarazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="e01d0-131">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="e01d0-132">In una dichiarazione di interfaccia, il codice seguente non dichiara `class` `struct`una proprietà implementata automaticamente come in un oggetto o .</span><span class="sxs-lookup"><span data-stu-id="e01d0-132">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="e01d0-133">Al contrario, dichiara una proprietà che non dispone di un'implementazione predefinita, ma deve essere implementata in qualsiasi tipo che implementa l'interfaccia:Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span><span class="sxs-lookup"><span data-stu-id="e01d0-133">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="e01d0-134">Un'interfaccia può ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="e01d0-134">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="e01d0-135">Quando un'interfaccia [esegue l'override](override.md) di un metodo implementato in un'interfaccia di base, deve utilizzare la sintassi di implementazione esplicita [dell'interfaccia.](../../programming-guide/interfaces/explicit-interface-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="e01d0-135">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="e01d0-136">Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.</span><span class="sxs-lookup"><span data-stu-id="e01d0-136">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="e01d0-137">Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-137">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="e01d0-138">Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-138">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="e01d0-139">Inoltre, è possibile accedere ai membri di interfaccia predefiniti solo tramite un'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-139">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="e01d0-140">Per ulteriori informazioni sull'implementazione esplicita dell'interfaccia, vedere [Implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="e01d0-140">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="e01d0-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="e01d0-141">Example</span></span>

<span data-ttu-id="e01d0-142">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e01d0-142">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="e01d0-143">In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e01d0-143">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="e01d0-144">Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="e01d0-144">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="e01d0-145">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e01d0-145">C# language specification</span></span>

<span data-ttu-id="e01d0-146">Per altre informazioni, vedere la sezione [Interfaces](~/_csharplang/spec/interfaces.md) della specifica del [linguaggio C'](~/_csharplang/spec/introduction.md) e la specifica della funzionalità per i [membri dell'interfaccia predefinita - C](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span><span class="sxs-lookup"><span data-stu-id="e01d0-146">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="e01d0-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e01d0-147">See also</span></span>

- [<span data-ttu-id="e01d0-148">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e01d0-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e01d0-149">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e01d0-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e01d0-150">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e01d0-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e01d0-151">Tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="e01d0-151">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="e01d0-152">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e01d0-152">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="e01d0-153">Utilizzo delle proprietà</span><span class="sxs-lookup"><span data-stu-id="e01d0-153">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="e01d0-154">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="e01d0-154">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="e01d0-155">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e01d0-155">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
