---
title: Generics - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: c7252180c9c98a8ca99c8cc6b3faaf8b1b8f0749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79167492"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="0cefb-102">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0cefb-102">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="0cefb-103">I generics introducono il concetto di parametri di tipo in .NET Framework, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi fino a quando la classe o il metodo non viene dichiarata e creata un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="0cefb-103">Generics introduce the concept of type parameters to the .NET Framework, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="0cefb-104">Ad esempio, utilizzando un `T`parametro di tipo generico , è possibile scrivere una singola classe che può essere utilizzata da altro codice client senza incorrere nel costo o nel rischio di eseguire cast di runtime o operazioni di boxing, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0cefb-104">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="0cefb-105">Le classi e i metodi generici combinano riusabilità, indipendenza dai tipi ed efficienza in un modo che le loro controparti non generiche non possono.</span><span class="sxs-lookup"><span data-stu-id="0cefb-105">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="0cefb-106">I generics sono in genere usati con le raccolte e i metodi che operano su di essi.</span><span class="sxs-lookup"><span data-stu-id="0cefb-106">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="0cefb-107">Lo <xref:System.Collections.Generic> spazio dei nomi contiene diverse classi di raccolte basate su generici.</span><span class="sxs-lookup"><span data-stu-id="0cefb-107">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="0cefb-108">Le raccolte non generiche, ad <xref:System.Collections.ArrayList> esempio non sono consigliate e vengono mantenute per motivi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="0cefb-108">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="0cefb-109">Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cefb-109">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="0cefb-110">Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti.</span><span class="sxs-lookup"><span data-stu-id="0cefb-110">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="0cefb-111">Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="0cefb-111">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="0cefb-112">Nella maggior parte dei casi, è consigliabile utilizzare la <xref:System.Collections.Generic.List%601> classe fornita dalla libreria di classi .NET Framework anziché crearne una personalizzata. Il parametro `T` type viene utilizzato in diverse posizioni in cui un tipo concreto viene in genere utilizzato per indicare il tipo di elemento archiviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0cefb-112">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="0cefb-113">In particolare, viene usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="0cefb-113">It is used in the following ways:</span></span>

- <span data-ttu-id="0cefb-114">Come tipo di un parametro del metodo nel metodo `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="0cefb-114">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="0cefb-115">Come tipo restituito della proprietà `Data` nella classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="0cefb-115">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="0cefb-116">Come tipo del membro privato `data` nella classe annidata.</span><span class="sxs-lookup"><span data-stu-id="0cefb-116">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="0cefb-117">Si `T` noti che `Node` è disponibile per la classe annidata.</span><span class="sxs-lookup"><span data-stu-id="0cefb-117">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="0cefb-118">Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.</span><span class="sxs-lookup"><span data-stu-id="0cefb-118">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="0cefb-119">Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi.</span><span class="sxs-lookup"><span data-stu-id="0cefb-119">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="0cefb-120">Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="0cefb-120">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="0cefb-121">Panoramica dei generici</span><span class="sxs-lookup"><span data-stu-id="0cefb-121">Generics overview</span></span>

- <span data-ttu-id="0cefb-122">Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0cefb-122">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="0cefb-123">L'uso più comune dei generics consiste nel creare classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="0cefb-123">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="0cefb-124">La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="0cefb-124">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="0cefb-125">Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="0cefb-125">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="0cefb-126">È possibile creare interfacce, classi, metodi, eventi e delegati generici personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0cefb-126">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="0cefb-127">Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="0cefb-127">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="0cefb-128">Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0cefb-128">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0cefb-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0cefb-129">Related sections</span></span>

- [<span data-ttu-id="0cefb-130">Parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="0cefb-130">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="0cefb-131">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0cefb-131">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="0cefb-132">Classi genericheGeneric Classes</span><span class="sxs-lookup"><span data-stu-id="0cefb-132">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="0cefb-133">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="0cefb-133">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="0cefb-134">Metodi Generic</span><span class="sxs-lookup"><span data-stu-id="0cefb-134">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="0cefb-135">Delegati generici</span><span class="sxs-lookup"><span data-stu-id="0cefb-135">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="0cefb-136">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="0cefb-136">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="0cefb-137">Generics e reflection</span><span class="sxs-lookup"><span data-stu-id="0cefb-137">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="0cefb-138">Generics in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0cefb-138">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="0cefb-139">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0cefb-139">C# language specification</span></span>

<span data-ttu-id="0cefb-140">Per ulteriori informazioni, vedere la [specifica del linguaggio C .](~/_csharplang/spec/types.md#constructed-types)</span><span class="sxs-lookup"><span data-stu-id="0cefb-140">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cefb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cefb-141">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="0cefb-142">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0cefb-142">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0cefb-143">Tipi</span><span class="sxs-lookup"><span data-stu-id="0cefb-143">Types</span></span>](../types/index.md)
- [<span data-ttu-id="0cefb-144">\<>typeparam</span><span class="sxs-lookup"><span data-stu-id="0cefb-144">\<typeparam></span></span>](../xmldoc/typeparam.md)
- [<span data-ttu-id="0cefb-145">\<>typeparamref</span><span class="sxs-lookup"><span data-stu-id="0cefb-145">\<typeparamref></span></span>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="0cefb-146">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="0cefb-146">Generics in .NET</span></span>](../../../standard/generics/index.md)
