---
title: Operatore new - Riferimenti per C#
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 84131bc503a106961419a27fc4e3e0f2d82306a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846233"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="68a28-102">Operatore new (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="68a28-102">new operator (C# reference)</span></span>

<span data-ttu-id="68a28-103">L'operatore `new` consente di creare una nuova istanza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="68a28-103">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="68a28-104">È anche possibile usare la parola chiave `new` come [modificatore di dichiarazione di membro](../keywords/new-modifier.md) o come [vincolo di tipo generico](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="68a28-104">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="68a28-105">Chiamata di un costruttore</span><span class="sxs-lookup"><span data-stu-id="68a28-105">Constructor invocation</span></span>

<span data-ttu-id="68a28-106">Per creare una nuova istanza di un tipo, in genere si chiama uno dei [costruttori](../../programming-guide/classes-and-structs/constructors.md) del tipo in questione tramite l'operatore `new`:</span><span class="sxs-lookup"><span data-stu-id="68a28-106">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/NewOperator.cs#Constructor)]

<span data-ttu-id="68a28-107">È possibile usare un [inizializzatore di oggetto o insieme](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) con l'operatore `new` per creare un'istanza di un oggetto e inizializzare l'oggetto in un'unica istruzione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="68a28-107">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a><span data-ttu-id="68a28-108">creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="68a28-108">Array creation</span></span>

<span data-ttu-id="68a28-109">È possibile usare l'operatore `new` per creare un'istanza di matrice, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="68a28-109">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/NewOperator.cs#Array)]

<span data-ttu-id="68a28-110">Usare la sintassi di inizializzazione di una matrice per creare un'istanza di una matrice e popolarla con elementi in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="68a28-110">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="68a28-111">L'esempio seguente illustra diversi modi per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="68a28-111">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="68a28-112">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="68a28-112">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="68a28-113">Creazione di istanze di tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="68a28-113">Instantiation of anonymous types</span></span>

<span data-ttu-id="68a28-114">Per creare un'istanza di un [tipo anonimo](../../programming-guide/classes-and-structs/anonymous-types.md), usare l'operatore `new` e la sintassi dell'inizializzatore di oggetto:</span><span class="sxs-lookup"><span data-stu-id="68a28-114">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="68a28-115">Eliminazione di istanze di tipi</span><span class="sxs-lookup"><span data-stu-id="68a28-115">Destruction of type instances</span></span>

<span data-ttu-id="68a28-116">Non è necessario eliminare definitivamente istanze di tipi create in precedenza.</span><span class="sxs-lookup"><span data-stu-id="68a28-116">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="68a28-117">Le istanze dei tipi riferimento e valore vengono eliminate definitivamente in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="68a28-117">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="68a28-118">Le istanze dei tipi valore vengono eliminate definitivamente non appena viene eliminato definitivamente il contesto che le contiene.</span><span class="sxs-lookup"><span data-stu-id="68a28-118">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="68a28-119">Le istanze dei tipi riferimento vengono eliminate definitivamente dal [Garbage Collector](../../../standard/garbage-collection/index.md) in un momento non specificato dopo che è stato rimosso l'ultimo riferimento ad esse.</span><span class="sxs-lookup"><span data-stu-id="68a28-119">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="68a28-120">Per le istanze di tipo che contengono risorse non gestite, ad esempio un handle di file, è consigliabile utilizzare la pulizia deterministica per garantire che le risorse in esse contenute vengano rilasciate il prima possibile.</span><span class="sxs-lookup"><span data-stu-id="68a28-120">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="68a28-121">Per altre informazioni, vedere le informazioni di riferimento dell'API <xref:System.IDisposable?displayProperty=nameWithType> e l'articolo sull'[ istruzione using ](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="68a28-121">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="68a28-122">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="68a28-122">Operator overloadability</span></span>

<span data-ttu-id="68a28-123">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="68a28-123">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="68a28-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="68a28-124">C# language specification</span></span>

<span data-ttu-id="68a28-125">Per altre informazioni, vedere la sezione [Operatore new](~/_csharplang/spec/expressions.md#the-new-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="68a28-125">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68a28-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68a28-126">See also</span></span>

- [<span data-ttu-id="68a28-127">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="68a28-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="68a28-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="68a28-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="68a28-129">Inizializzatori di oggetto e di insieme</span><span class="sxs-lookup"><span data-stu-id="68a28-129">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
