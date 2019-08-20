---
title: Generics - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 7d212aeaa7d7a8c3f152f8610a7ef3fe5de0fe23
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589600"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="c2411-102">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c2411-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="c2411-103">I generics sono stati aggiunti alla versione 2.0 del linguaggio C# e di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c2411-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="c2411-104">I generics introducono in .NET Framework il concetto dei parametri di tipo, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi finché non si dichiara la classe o il metodo e si crea un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="c2411-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="c2411-105">Ad esempio, usando un parametro di tipo generico T è possibile scrivere un'unica classe che altro codice client può usare senza rischiare cast di runtime o operazioni di boxing, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c2411-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="c2411-106">Le classi e i metodi generici sono riutilizzabili, indipendenti dai tipi e molto più efficaci delle rispettive controparti non generiche.</span><span class="sxs-lookup"><span data-stu-id="c2411-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="c2411-107">I generics sono in genere usati con le raccolte e i metodi che operano su di essi.</span><span class="sxs-lookup"><span data-stu-id="c2411-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="c2411-108">La versione 2.0 della libreria di classi .NET Framework offre un nuovo spazio dei nomi, <xref:System.Collections.Generic>, che contiene diverse nuove classi di raccolta generiche.</span><span class="sxs-lookup"><span data-stu-id="c2411-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="c2411-109">È consigliabile che tutte le applicazioni destinate a .NET Framework 2.0 e versioni successive usino le nuove classi di raccolte generiche anziché le controparti non generiche meno recenti, ad esempio <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="c2411-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="c2411-110">Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="c2411-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="c2411-111">Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti.</span><span class="sxs-lookup"><span data-stu-id="c2411-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="c2411-112">Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="c2411-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="c2411-113">Nella maggior parte dei casi, è necessario usare la classe <xref:System.Collections.Generic.List%601> specificata dalla libreria di classi .NET Framework anziché crearne una propria. Il parametro di tipo `T` viene usato in diverse posizioni in cui di norma verrebbe usato un tipo concreto per indicare il tipo dell'elemento archiviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c2411-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="c2411-114">In particolare, viene usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="c2411-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="c2411-115">Come tipo di un parametro del metodo nel metodo `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="c2411-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="c2411-116">Come tipo restituito della proprietà `Data` nella classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="c2411-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="c2411-117">Come tipo del membro privato `data` nella classe annidata.</span><span class="sxs-lookup"><span data-stu-id="c2411-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="c2411-118">Si noti che T è disponibile per la classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="c2411-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="c2411-119">Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.</span><span class="sxs-lookup"><span data-stu-id="c2411-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="c2411-120">Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi.</span><span class="sxs-lookup"><span data-stu-id="c2411-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="c2411-121">Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="c2411-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="c2411-122">Panoramica sui generics</span><span class="sxs-lookup"><span data-stu-id="c2411-122">Generics Overview</span></span>  
  
- <span data-ttu-id="c2411-123">Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c2411-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="c2411-124">L'uso più comune dei generics consiste nel creare classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="c2411-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="c2411-125">La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="c2411-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="c2411-126">Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="c2411-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="c2411-127">È possibile creare interfacce, classi, metodi, eventi e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="c2411-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="c2411-128">Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="c2411-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="c2411-129">Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c2411-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c2411-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c2411-130">Related Sections</span></span>  
 <span data-ttu-id="c2411-131">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="c2411-131">For more information:</span></span>  
  
- [<span data-ttu-id="c2411-132">Parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="c2411-132">Generic Type Parameters</span></span>](./generic-type-parameters.md)  
  
- [<span data-ttu-id="c2411-133">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c2411-133">Constraints on Type Parameters</span></span>](./constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="c2411-134">Classi generiche</span><span class="sxs-lookup"><span data-stu-id="c2411-134">Generic Classes</span></span>](./generic-classes.md)  
  
- [<span data-ttu-id="c2411-135">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="c2411-135">Generic Interfaces</span></span>](./generic-interfaces.md)  
  
- [<span data-ttu-id="c2411-136">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="c2411-136">Generic Methods</span></span>](./generic-methods.md)  
  
- [<span data-ttu-id="c2411-137">Delegati generici</span><span class="sxs-lookup"><span data-stu-id="c2411-137">Generic Delegates</span></span>](./generic-delegates.md)  
  
- [<span data-ttu-id="c2411-138">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="c2411-138">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="c2411-139">Generics e reflection</span><span class="sxs-lookup"><span data-stu-id="c2411-139">Generics and Reflection</span></span>](./generics-and-reflection.md)  
  
- [<span data-ttu-id="c2411-140">Generics in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c2411-140">Generics in the Run Time</span></span>](./generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c2411-141">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c2411-141">C# Language Specification</span></span>  
 <span data-ttu-id="c2411-142">Per altre informazioni, vedere la [specifica del linguaggio C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="c2411-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2411-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2411-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="c2411-144">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c2411-144">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c2411-145">Tipi</span><span class="sxs-lookup"><span data-stu-id="c2411-145">Types</span></span>](../types/index.md)
- [<span data-ttu-id="c2411-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="c2411-146">\<typeparam></span></span>](../xmldoc/typeparam.md)
- [<span data-ttu-id="c2411-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="c2411-147">\<typeparamref></span></span>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="c2411-148">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="c2411-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
