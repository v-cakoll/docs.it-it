---
title: Generics (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 026b8350a75794cf1101bef69d1bf15f474f103d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="ae4ce-102">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ae4ce-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="ae4ce-103">I generics sono stati aggiunti alla versione 2.0 del linguaggio C# e di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ae4ce-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="ae4ce-104">I generics introducono in .NET Framework il concetto dei parametri di tipo, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi finché non si dichiara la classe o il metodo e si crea un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="ae4ce-105">Ad esempio, usando un parametro di tipo generico T è possibile scrivere un'unica classe che altro codice client può usare senza rischiare cast di runtime o operazioni di boxing, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae4ce-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a><span data-ttu-id="ae4ce-106">Panoramica sui generics</span><span class="sxs-lookup"><span data-stu-id="ae4ce-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="ae4ce-107">Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="ae4ce-108">L'uso più comune dei generics consiste nel creare classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="ae4ce-109">La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="ae4ce-110">Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="ae4ce-111">È possibile creare interfacce, classi, metodi, eventi e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="ae4ce-112">Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="ae4ce-113">Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ae4ce-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ae4ce-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ae4ce-114">Related Sections</span></span>  
 <span data-ttu-id="ae4ce-115">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="ae4ce-115">For more information:</span></span>  
  
-   [<span data-ttu-id="ae4ce-116">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="ae4ce-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="ae4ce-117">Vantaggi dei generics</span><span class="sxs-lookup"><span data-stu-id="ae4ce-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="ae4ce-118">Parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="ae4ce-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="ae4ce-119">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="ae4ce-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="ae4ce-120">Classi generiche</span><span class="sxs-lookup"><span data-stu-id="ae4ce-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="ae4ce-121">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="ae4ce-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="ae4ce-122">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="ae4ce-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="ae4ce-123">Delegati generici</span><span class="sxs-lookup"><span data-stu-id="ae4ce-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="ae4ce-124">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="ae4ce-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="ae4ce-125">Generics e reflection</span><span class="sxs-lookup"><span data-stu-id="ae4ce-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="ae4ce-126">Generics in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ae4ce-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ae4ce-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ae4ce-127">C# Language Specification</span></span>  
 <span data-ttu-id="ae4ce-128">Per altre informazioni, vedere la [specifica del linguaggio C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ae4ce-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4ce-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae4ce-129">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="ae4ce-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ae4ce-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ae4ce-131">Tipi</span><span class="sxs-lookup"><span data-stu-id="ae4ce-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="ae4ce-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="ae4ce-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)  
 [<span data-ttu-id="ae4ce-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="ae4ce-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)  
 [<span data-ttu-id="ae4ce-134">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="ae4ce-134">Generics in .NET</span></span>](../../../standard/generics/index.md)  