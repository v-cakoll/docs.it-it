---
title: Membri con corpo di espressione - Guida per programmatori C#
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711987"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="2f6e9-102">Membri con corpo di espressione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2f6e9-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="2f6e9-103">Le definizioni dei corpi di espressione consentono di eseguire l'implementazione di un membro in un modulo molto conciso e leggibile.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="2f6e9-104">È possibile usare una definizione di corpo di espressione ogni volta che la logica per un membro supportato, ad esempio un metodo o proprietà, è costituita da un'unica espressione.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="2f6e9-105">Una definizione di corpo di espressione presenta la seguente sintassi generale:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="2f6e9-106">dove *expression* è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="2f6e9-107">Il supporto per le definizioni dei corpi di espressione è stato introdotto per i metodi e le proprietà di sola lettura in C# 6 ed è stato ampliato in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="2f6e9-108">Le definizioni dei corpi di espressione possono essere usate con i membri dei tipi elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="2f6e9-109">Membro</span><span class="sxs-lookup"><span data-stu-id="2f6e9-109">Member</span></span>  |<span data-ttu-id="2f6e9-110">Supportato a partire da...</span><span class="sxs-lookup"><span data-stu-id="2f6e9-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="2f6e9-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="2f6e9-111">Method</span></span>](#methods)  |<span data-ttu-id="2f6e9-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="2f6e9-112">C# 6</span></span> |
|[<span data-ttu-id="2f6e9-113">Proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="2f6e9-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="2f6e9-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="2f6e9-114">C# 6</span></span>  |
|[<span data-ttu-id="2f6e9-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2f6e9-115">Property</span></span>](#properties)  |<span data-ttu-id="2f6e9-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="2f6e9-116">C# 7.0</span></span> |
|[<span data-ttu-id="2f6e9-117">Costruttore</span><span class="sxs-lookup"><span data-stu-id="2f6e9-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="2f6e9-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="2f6e9-118">C# 7.0</span></span> |
|[<span data-ttu-id="2f6e9-119">Finalizer</span><span class="sxs-lookup"><span data-stu-id="2f6e9-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="2f6e9-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="2f6e9-120">C# 7.0</span></span> |
|[<span data-ttu-id="2f6e9-121">Indicizzatore</span><span class="sxs-lookup"><span data-stu-id="2f6e9-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="2f6e9-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="2f6e9-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="2f6e9-123">Metodi</span><span class="sxs-lookup"><span data-stu-id="2f6e9-123">Methods</span></span>

<span data-ttu-id="2f6e9-124">Un metodo con corpo di espressione è costituito da una singola espressione che restituisce un valore il cui tipo corrisponde al tipo restituito del metodo oppure, per i metodi che restituiscono `void`, che esegue una determinata operazione.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="2f6e9-125">Ad esempio, i tipi che eseguono l'override del metodo <xref:System.Object.ToString%2A> di solito includono una singola espressione che restituisce la rappresentazione di stringa dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="2f6e9-126">L'esempio seguente definisce una classe `Person` che esegue l'override del metodo <xref:System.Object.ToString%2A> con una definizione di corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="2f6e9-127">Definisce inoltre un metodo `DisplayName` che visualizza un nome nella console.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="2f6e9-128">Si noti che la parola chiave `return` non viene usata nella definizione del corpo di espressione `ToString`.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="2f6e9-129">Per altre informazioni, vedere [Metodi (Guida per programmatori C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="2f6e9-130">Proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="2f6e9-130">Read-only properties</span></span>

<span data-ttu-id="2f6e9-131">A partire da C# 6, è possibile usare una definizione del corpo dell'espressione per implementare una proprietà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="2f6e9-132">A questo scopo, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="2f6e9-133">L'esempio seguente definisce una classe `Location` la cui proprietà `Name` di sola lettura viene implementata come definizione del corpo dell'espressione che restituisce il valore del campo `locationName` privato:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="2f6e9-134">Per altre informazioni sulle proprietà, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="2f6e9-135">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2f6e9-135">Properties</span></span>

<span data-ttu-id="2f6e9-136">A partire da C# 7.0, è possibile usare definizioni del corpo dell'espressione per implementare la proprietà `get` e le funzioni di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="2f6e9-137">Nell'esempio riportato di seguito viene illustrato come procedere:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="2f6e9-138">Per altre informazioni sulle proprietà, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="2f6e9-139">Costruttori</span><span class="sxs-lookup"><span data-stu-id="2f6e9-139">Constructors</span></span>

<span data-ttu-id="2f6e9-140">Una definizione di corpo di espressione per un costruttore in genere è costituita da una singola espressione di assegnazione o da una chiamata al metodo che gestisce gli argomenti del costruttore o inizializza lo stato dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="2f6e9-141">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="2f6e9-142">La definizione del corpo dell'espressione assegna l'argomento alla proprietà `Name`.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="2f6e9-143">Per altre informazioni, vedere [Costruttori (Guida per programmatori C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="2f6e9-144">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="2f6e9-144">Finalizers</span></span>

<span data-ttu-id="2f6e9-145">Una definizione di corpo di espressione per un finalizzatore in genere contiene istruzioni di pulitura, ad esempio le istruzioni che rilasciano risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="2f6e9-146">L'esempio seguente definisce un finalizzatore che usa una definizione di corpo di espressione per indicare che è stato chiamato il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="2f6e9-147">Per altre informazioni, vedere [Finalizzatori (Guida per programmatori C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="2f6e9-148">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="2f6e9-148">Indexers</span></span>

<span data-ttu-id="2f6e9-149">Come con le `get` proprietà, indicizzatore e `set` funzioni `get` di accesso sono costituite da definizioni del corpo dell'espressione se la funzione di accesso è costituita da una singola espressione che restituisce un valore o la `set` funzione di accesso esegue un'assegnazione semplice.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="2f6e9-150">Nell'esempio seguente viene definita una classe denominata `Sports` che include una matrice <xref:System.String> interna contenente i nomi di alcuni sport.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="2f6e9-151">Sia l'indicizzatore `get` che `set` le funzioni di accesso vengono implementate come definizioni del corpo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="2f6e9-152">Per altre informazioni, vedere [Indicizzatori (Guida per programmatori C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e9-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
