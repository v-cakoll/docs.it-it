---
title: Membri con corpo di espressione (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5690a2ddb9127bb0c9b06d3607e3d105fca9a2e8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="8d504-102">Membri con corpo di espressione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8d504-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="8d504-103">Le definizioni dei corpi di espressione consentono di eseguire l'implementazione di un membro in un modulo molto conciso e leggibile.</span><span class="sxs-lookup"><span data-stu-id="8d504-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="8d504-104">È possibile usare una definizione di corpo di espressione ogni volta che la logica per un membro supportato, ad esempio un metodo o proprietà, è costituita da un'unica espressione.</span><span class="sxs-lookup"><span data-stu-id="8d504-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="8d504-105">Una definizione di corpo di espressione presenta la seguente sintassi generale:</span><span class="sxs-lookup"><span data-stu-id="8d504-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="8d504-106">dove *expression* è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="8d504-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="8d504-107">Il supporto per le definizioni dei corpi di espressione è stato introdotto per i metodi e le funzioni di accesso Property Get in C# 6 ed è stato ampliato in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="8d504-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="8d504-108">Le definizioni dei corpi di espressione possono essere usate con i membri dei tipi elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8d504-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="8d504-109">Member</span><span class="sxs-lookup"><span data-stu-id="8d504-109">Member</span></span>  |<span data-ttu-id="8d504-110">Supportato a partire da...</span><span class="sxs-lookup"><span data-stu-id="8d504-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="8d504-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="8d504-111">Method</span></span>](#methods)  |<span data-ttu-id="8d504-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="8d504-112">C# 6</span></span> |
|[<span data-ttu-id="8d504-113">Costruttore</span><span class="sxs-lookup"><span data-stu-id="8d504-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="8d504-114">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="8d504-114">C# 7.0</span></span> |
|[<span data-ttu-id="8d504-115">Finalizzatore</span><span class="sxs-lookup"><span data-stu-id="8d504-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="8d504-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="8d504-116">C# 7.0</span></span> |
|[<span data-ttu-id="8d504-117">Property Get</span><span class="sxs-lookup"><span data-stu-id="8d504-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="8d504-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="8d504-118">C# 6</span></span> |
|[<span data-ttu-id="8d504-119">Property Set</span><span class="sxs-lookup"><span data-stu-id="8d504-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="8d504-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="8d504-120">C# 7.0</span></span> |
|[<span data-ttu-id="8d504-121">Indicizzatore</span><span class="sxs-lookup"><span data-stu-id="8d504-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="8d504-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="8d504-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="8d504-123">Metodi</span><span class="sxs-lookup"><span data-stu-id="8d504-123">Methods</span></span>

<span data-ttu-id="8d504-124">Un metodo con corpo di espressione è costituito da una singola espressione che restituisce un valore il cui tipo corrisponde al tipo restituito del metodo oppure, per i metodi che restituiscono `void`, che esegue una determinata operazione.</span><span class="sxs-lookup"><span data-stu-id="8d504-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="8d504-125">Ad esempio, i tipi che eseguono l'override del metodo <xref:System.Object.ToString%2A> di solito includono una singola espressione che restituisce la rappresentazione di stringa dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="8d504-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="8d504-126">L'esempio seguente definisce una classe `Person` che esegue l'override del metodo <xref:System.Object.ToString%2A> con una definizione di corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="8d504-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="8d504-127">Definisce inoltre un metodo `Show` che visualizza un nome nella console.</span><span class="sxs-lookup"><span data-stu-id="8d504-127">It also defines a `Show` method that displays a name to the console.</span></span> <span data-ttu-id="8d504-128">Si noti che la parola chiave `return` non viene usata nella definizione del corpo di espressione `ToString`.</span><span class="sxs-lookup"><span data-stu-id="8d504-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="8d504-129">Per altre informazioni, vedere [Metodi (Guida per programmatori C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="8d504-130">Costruttori</span><span class="sxs-lookup"><span data-stu-id="8d504-130">Constructors</span></span>

<span data-ttu-id="8d504-131">Una definizione di corpo di espressione per un costruttore in genere è costituita da una singola espressione di assegnazione o da una chiamata al metodo che gestisce gli argomenti del costruttore o inizializza lo stato dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="8d504-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="8d504-132">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="8d504-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="8d504-133">La definizione del corpo dell'espressione assegna l'argomento alla proprietà `Name`.</span><span class="sxs-lookup"><span data-stu-id="8d504-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="8d504-134">Per altre informazioni, vedere [Costruttori (Guida per programmatori C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="8d504-135">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="8d504-135">Finalizers</span></span>

<span data-ttu-id="8d504-136">Una definizione di corpo di espressione per un finalizzatore in genere contiene istruzioni di pulitura, ad esempio le istruzioni che rilasciano risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="8d504-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="8d504-137">L'esempio seguente definisce un finalizzatore che usa una definizione di corpo di espressione per indicare che è stato chiamato il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="8d504-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="8d504-138">Per altre informazioni, vedere [Finalizzatori (Guida per programmatori C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="8d504-139">Istruzioni Property Get</span><span class="sxs-lookup"><span data-stu-id="8d504-139">Property get statements</span></span>

<span data-ttu-id="8d504-140">Se si sceglie di implementare manualmente una funzione di accesso Property Get, è possibile usare una definizione di corpo di espressione per singole espressioni che restituiscono semplicemente il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d504-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="8d504-141">Si noti che l'istruzione `return` non viene usata.</span><span class="sxs-lookup"><span data-stu-id="8d504-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="8d504-142">L'esempio seguente definisce una proprietà `Location.Name` la cui funzione di accesso Property Get restituisce il valore del campo `locationName` privato sottostante alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d504-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="8d504-143">Le proprietà di sola lettura che usano una definizione di corpo di espressione possono essere implementate senza un'istruzione `set` esplicita.</span><span class="sxs-lookup"><span data-stu-id="8d504-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="8d504-144">La sintassi è:</span><span class="sxs-lookup"><span data-stu-id="8d504-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="8d504-145">L'esempio seguente definisce una classe `Location` la cui proprietà `Name` di sola lettura viene implementata come definizione del corpo dell'espressione che restituisce il valore del campo `locationName` privato.</span><span class="sxs-lookup"><span data-stu-id="8d504-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="8d504-146">Per altre informazioni, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="8d504-147">Istruzioni Property Set</span><span class="sxs-lookup"><span data-stu-id="8d504-147">Property set statements</span></span>

<span data-ttu-id="8d504-148">Se si sceglie di implementare manualmente una funzione di accesso Property Set, è possibile usare una definizione di corpo di espressione per un'espressione a riga singola che assegna un valore al campo sottostante alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d504-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="8d504-149">L'esempio seguente definisce una proprietà `Location.Name` la cui istruzione Property Set assegna il proprio argomento di input al campo `locationName` privato sottostante alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="8d504-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="8d504-150">Per altre informazioni, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="8d504-151">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="8d504-151">Indexers</span></span>

<span data-ttu-id="8d504-152">Analogamente alle proprietà, le funzioni di accesso get e set di un indicizzatore sono costituite da definizioni di corpi di espressione se la funzione di accesso get è costituita da una singola istruzione che restituisce un valore o la funzione di accesso set esegue un'assegnazione semplice.</span><span class="sxs-lookup"><span data-stu-id="8d504-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="8d504-153">Nell'esempio seguente viene definita una classe denominata `Sports` che include una matrice <xref:System.String> interna contenente i nomi di alcuni sport.</span><span class="sxs-lookup"><span data-stu-id="8d504-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="8d504-154">Le funzioni di accesso sia get che set dell'indicizzatore vengono implementate come definizioni di corpi di espressione.</span><span class="sxs-lookup"><span data-stu-id="8d504-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="8d504-155">Per altre informazioni, vedere [Indicizzatori (Guida per programmatori C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="8d504-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

