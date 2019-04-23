---
title: Generics - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 186c5bc91204770e636eed5c008db23b798b6880
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710251"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="2418b-102">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2418b-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="2418b-103">I generics sono stati aggiunti alla versione 2.0 del linguaggio C# e di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2418b-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="2418b-104">I generics introducono in .NET Framework il concetto dei parametri di tipo, che consentono di progettare classi e metodi che rinviano la specifica di uno o più tipi finché non si dichiara la classe o il metodo e si crea un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="2418b-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="2418b-105">Ad esempio, usando un parametro di tipo generico T è possibile scrivere un'unica classe che altro codice client può usare senza rischiare cast di runtime o operazioni di boxing, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2418b-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  
  
## <a name="generics-overview"></a><span data-ttu-id="2418b-106">Panoramica sui generics</span><span class="sxs-lookup"><span data-stu-id="2418b-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="2418b-107">Usare i tipi generici per ottimizzare il riutilizzo del codice, l'indipendenza dai tipi e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2418b-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="2418b-108">L'uso più comune dei generics consiste nel creare classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="2418b-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="2418b-109">La libreria di classi .NET Framework contiene diverse nuove classi di raccolte generiche nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="2418b-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="2418b-110">Queste classi devono essere usate ogni volta che sia possibile al posto di classi come <xref:System.Collections.ArrayList> nello spazio dei nomi <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="2418b-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="2418b-111">È possibile creare interfacce, classi, metodi, eventi e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="2418b-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="2418b-112">Le classi generiche possono essere limitate in modo da abilitare l'accesso ai metodi per particolari tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="2418b-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="2418b-113">Le informazioni sui tipi usati in un tipo di dati generico possono essere ottenute usando la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2418b-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2418b-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="2418b-114">Related Sections</span></span>  
 <span data-ttu-id="2418b-115">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="2418b-115">For more information:</span></span>  
  
-   [<span data-ttu-id="2418b-116">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="2418b-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="2418b-117">Vantaggi dei generics</span><span class="sxs-lookup"><span data-stu-id="2418b-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="2418b-118">Parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="2418b-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="2418b-119">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2418b-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="2418b-120">Classi generiche</span><span class="sxs-lookup"><span data-stu-id="2418b-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="2418b-121">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="2418b-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="2418b-122">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="2418b-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="2418b-123">Delegati generici</span><span class="sxs-lookup"><span data-stu-id="2418b-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="2418b-124">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="2418b-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="2418b-125">Generics e reflection</span><span class="sxs-lookup"><span data-stu-id="2418b-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="2418b-126">Generics in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2418b-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="2418b-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2418b-127">C# Language Specification</span></span>  
 <span data-ttu-id="2418b-128">Per altre informazioni, vedere la [specifica del linguaggio C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="2418b-128">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2418b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2418b-129">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="2418b-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2418b-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2418b-131">Tipi</span><span class="sxs-lookup"><span data-stu-id="2418b-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="2418b-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="2418b-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="2418b-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="2418b-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="2418b-134">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="2418b-134">Generics in .NET</span></span>](../../../standard/generics/index.md)
