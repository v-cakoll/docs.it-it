---
title: interface - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 058d6b96e96a3237ebac2ca079807fd154715d68
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608656"
---
# <a name="interface-c-reference"></a><span data-ttu-id="53f15-102">interface (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="53f15-102">interface (C# Reference)</span></span>

<span data-ttu-id="53f15-103">Un'interfaccia contiene solo le firme di [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [eventi](../../programming-guide/events/index.md) o [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="53f15-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="53f15-104">Una classe o uno struct che implementa l'interfaccia deve implementarne i membri specificati nella definizione dell'interfaccia stessa.</span><span class="sxs-lookup"><span data-stu-id="53f15-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="53f15-105">Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="53f15-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="53f15-106">Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="53f15-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="53f15-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="53f15-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="53f15-108">Un'interfaccia può essere membro di uno spazio dei nomi o di una classe e contenere firme dei seguenti membri:</span><span class="sxs-lookup"><span data-stu-id="53f15-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="53f15-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="53f15-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="53f15-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="53f15-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="53f15-111">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="53f15-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="53f15-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="53f15-112">Events</span></span>](event.md)

<span data-ttu-id="53f15-113">Un'interfaccia può ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="53f15-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="53f15-114">Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.</span><span class="sxs-lookup"><span data-stu-id="53f15-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="53f15-115">Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53f15-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="53f15-116">Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53f15-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="53f15-117">Per altri dettagli e altri esempi di codice sull'implementazione esplicita delle interfacce, vedere [Implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="53f15-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="53f15-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="53f15-118">Example</span></span>

<span data-ttu-id="53f15-119">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53f15-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="53f15-120">In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="53f15-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="53f15-121">Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="53f15-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="53f15-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="53f15-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="53f15-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53f15-123">See also</span></span>

- [<span data-ttu-id="53f15-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="53f15-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="53f15-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="53f15-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="53f15-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="53f15-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="53f15-127">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="53f15-127">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="53f15-128">Interfacce</span><span class="sxs-lookup"><span data-stu-id="53f15-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="53f15-129">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="53f15-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="53f15-130">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="53f15-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="53f15-131">class</span><span class="sxs-lookup"><span data-stu-id="53f15-131">class</span></span>](class.md)
- [<span data-ttu-id="53f15-132">struct</span><span class="sxs-lookup"><span data-stu-id="53f15-132">struct</span></span>](struct.md)
- [<span data-ttu-id="53f15-133">Interfacce</span><span class="sxs-lookup"><span data-stu-id="53f15-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
