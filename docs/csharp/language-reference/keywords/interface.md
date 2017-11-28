---
title: interface (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: interface_CSharpKeyword
helpviewer_keywords: interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aba9ee66a90216066a47f22e251182caad465818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="interface-c-reference"></a><span data-ttu-id="49ce0-102">interface (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="49ce0-102">interface (C# Reference)</span></span>
<span data-ttu-id="49ce0-103">Un'interfaccia contiene solo le firme di [metodi](../../../csharp/programming-guide/classes-and-structs/methods.md), [proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), [eventi](../../../csharp/programming-guide/events/index.md) o [indicizzatori](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="49ce0-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="49ce0-104">Una classe o uno struct che implementa l'interfaccia deve implementarne i membri specificati nella definizione dell'interfaccia stessa.</span><span class="sxs-lookup"><span data-stu-id="49ce0-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="49ce0-105">Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="49ce0-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="49ce0-106">Per altre informazioni e altri esempi, vedere [Interfacce](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="49ce0-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ce0-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="49ce0-107">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 <span data-ttu-id="49ce0-108">Un'interfaccia può essere membro di uno spazio dei nomi o di una classe e contenere firme dei seguenti membri:</span><span class="sxs-lookup"><span data-stu-id="49ce0-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="49ce0-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="49ce0-109">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="49ce0-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="49ce0-110">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="49ce0-111">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="49ce0-111">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="49ce0-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="49ce0-112">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="49ce0-113">Un'interfaccia può ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="49ce0-113">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="49ce0-114">Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.</span><span class="sxs-lookup"><span data-stu-id="49ce0-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="49ce0-115">Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="49ce0-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="49ce0-116">Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="49ce0-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="49ce0-117">Per altri dettagli e altri esempi di codice sull'implementazione esplicita delle interfacce, vedere [Implementazione esplicita dell'interfaccia](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="49ce0-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ce0-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="49ce0-118">Example</span></span>  
 <span data-ttu-id="49ce0-119">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="49ce0-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="49ce0-120">In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="49ce0-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="49ce0-121">Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="49ce0-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="49ce0-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="49ce0-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49ce0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49ce0-123">See Also</span></span>  
 [<span data-ttu-id="49ce0-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="49ce0-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="49ce0-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="49ce0-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="49ce0-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="49ce0-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="49ce0-127">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="49ce0-127">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="49ce0-128">Interfacce</span><span class="sxs-lookup"><span data-stu-id="49ce0-128">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="49ce0-129">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="49ce0-129">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="49ce0-130">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="49ce0-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
 [<span data-ttu-id="49ce0-131">class</span><span class="sxs-lookup"><span data-stu-id="49ce0-131">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="49ce0-132">struct</span><span class="sxs-lookup"><span data-stu-id="49ce0-132">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="49ce0-133">Interfacce</span><span class="sxs-lookup"><span data-stu-id="49ce0-133">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
