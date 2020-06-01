---
title: Generics - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: a3ed3aa412c7d9c9d6b705dba80b527057c647fa
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241669"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="db4b5-102">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="db4b5-102">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="db4b5-103">I generics introducono il concetto di parametri di tipo in .NET, che rendono possibile la progettazione di classi e metodi che rinviano la specifica di uno o più tipi fino a quando la classe o il metodo non viene dichiarato e ne viene creata un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="db4b5-103">Generics introduce the concept of type parameters to .NET, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="db4b5-104">Usando, ad esempio, un parametro di tipo generico `T` , è possibile scrivere una singola classe che può essere usata da un altro codice client senza sostenere il costo o il rischio di cast di runtime o di operazioni di conversione boxing, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="db4b5-104">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="db4b5-105">Classi e metodi generici combinano riusabilità, indipendenza dai tipi ed efficienza in modo che non possano essere presenti controparti non generiche.</span><span class="sxs-lookup"><span data-stu-id="db4b5-105">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="db4b5-106">I generics sono in genere usati con le raccolte e i metodi che operano su di essi.</span><span class="sxs-lookup"><span data-stu-id="db4b5-106">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="db4b5-107">Lo <xref:System.Collections.Generic> spazio dei nomi contiene diverse classi di raccolta basate su generiche.</span><span class="sxs-lookup"><span data-stu-id="db4b5-107">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="db4b5-108">Le raccolte non generiche, ad esempio, <xref:System.Collections.ArrayList> non sono consigliate e vengono mantenute per motivi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="db4b5-108">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="db4b5-109">Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="db4b5-109">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="db4b5-110">Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti.</span><span class="sxs-lookup"><span data-stu-id="db4b5-110">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="db4b5-111">Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="db4b5-111">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="db4b5-112">Nella maggior parte dei casi, è consigliabile usare la <xref:System.Collections.Generic.List%601> classe fornita da .NET anziché crearne una personalizzata. Il parametro di tipo `T` viene usato in diverse posizioni in cui un tipo concreto viene normalmente usato per indicare il tipo di elemento archiviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="db4b5-112">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by .NET instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="db4b5-113">In particolare, viene usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="db4b5-113">It is used in the following ways:</span></span>

- <span data-ttu-id="db4b5-114">Come tipo di un parametro del metodo nel metodo `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="db4b5-114">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="db4b5-115">Come tipo restituito della proprietà `Data` nella classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="db4b5-115">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="db4b5-116">Come tipo del membro privato `data` nella classe annidata.</span><span class="sxs-lookup"><span data-stu-id="db4b5-116">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="db4b5-117">Si noti che `T` è disponibile per la `Node` classe annidata.</span><span class="sxs-lookup"><span data-stu-id="db4b5-117">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="db4b5-118">Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.</span><span class="sxs-lookup"><span data-stu-id="db4b5-118">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="db4b5-119">Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi.</span><span class="sxs-lookup"><span data-stu-id="db4b5-119">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="db4b5-120">Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="db4b5-120">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="db4b5-121">Cenni preliminari sui generics</span><span class="sxs-lookup"><span data-stu-id="db4b5-121">Generics overview</span></span>

- <span data-ttu-id="db4b5-122">Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="db4b5-122">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="db4b5-123">L'uso più comune dei generics consiste nel creare classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="db4b5-123">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="db4b5-124">La libreria di classi .NET contiene varie classi di raccolte generiche nello <xref:System.Collections.Generic> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="db4b5-124">The .NET class library contains several generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="db4b5-125">Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="db4b5-125">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="db4b5-126">È possibile creare interfacce, classi, metodi, eventi e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="db4b5-126">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="db4b5-127">Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="db4b5-127">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="db4b5-128">Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db4b5-128">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="db4b5-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="db4b5-129">Related sections</span></span>

- [<span data-ttu-id="db4b5-130">Parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="db4b5-130">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="db4b5-131">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="db4b5-131">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="db4b5-132">Classi generiche</span><span class="sxs-lookup"><span data-stu-id="db4b5-132">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="db4b5-133">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="db4b5-133">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="db4b5-134">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="db4b5-134">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="db4b5-135">Delegati generici</span><span class="sxs-lookup"><span data-stu-id="db4b5-135">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="db4b5-136">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="db4b5-136">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="db4b5-137">Generics e reflection</span><span class="sxs-lookup"><span data-stu-id="db4b5-137">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="db4b5-138">Generics in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="db4b5-138">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="db4b5-139">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="db4b5-139">C# language specification</span></span>

<span data-ttu-id="db4b5-140">Per ulteriori informazioni, vedere la [specifica del linguaggio C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="db4b5-140">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="db4b5-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db4b5-141">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="db4b5-142">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="db4b5-142">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="db4b5-143">Tipi</span><span class="sxs-lookup"><span data-stu-id="db4b5-143">Types</span></span>](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="db4b5-144">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="db4b5-144">Generics in .NET</span></span>](../../../standard/generics/index.md)
