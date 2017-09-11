---
title: Generics nel runtime (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 661dff2d8ec2e12ab6a459660a5378f74e93b9c5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generics-in-the-run-time-c-programming-guide"></a><span data-ttu-id="9881e-102">Generics nel runtime (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9881e-102">Generics in the Run Time (C# Programming Guide)</span></span>
<span data-ttu-id="9881e-103">Quando un tipo o un metodo generico viene compilato in Microsoft Intermediate Language (MSIL), contiene metadati che lo identificano come contenente parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="9881e-103">When a generic type or method is compiled into Microsoft intermediate language (MSIL), it contains metadata that identifies it as having type parameters.</span></span> <span data-ttu-id="9881e-104">L'uso di MSIL per un tipo generico differisce a seconda che il parametro di tipo sia un tipo valore o un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="9881e-104">How the MSIL for a generic type is used differs based on whether the supplied type parameter is a value type or reference type.</span></span>  
  
 <span data-ttu-id="9881e-105">La prima volta che viene costruito un tipo generico con un tipo valore come parametro, il runtime crea un tipo generico specializzato con il parametro o i parametri specificati sostituiti nelle posizioni appropriate in MSIL.</span><span class="sxs-lookup"><span data-stu-id="9881e-105">When a generic type is first constructed with a value type as a parameter, the runtime creates a specialized generic type with the supplied parameter or parameters substituted in the appropriate locations in the MSIL.</span></span> <span data-ttu-id="9881e-106">I tipi generici specializzati vengono creati una sola volta per ogni tipo valore univoco usato come parametro.</span><span class="sxs-lookup"><span data-stu-id="9881e-106">Specialized generic types are created one time for each unique value type that is used as a parameter.</span></span>  
  
 <span data-ttu-id="9881e-107">Ad esempio, si supponga che il codice programma abbia dichiarato uno stack costituito da interi:</span><span class="sxs-lookup"><span data-stu-id="9881e-107">For example, suppose your program code declared a stack that is constructed of integers:</span></span>  
  
 <span data-ttu-id="9881e-108">[!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-108">[!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]</span></span>  
  
 <span data-ttu-id="9881e-109">A questo punto, il runtime genera una versione specializzata della classe <xref:System.Collections.Generic.Stack%601> sostituendo l'intero nel modo appropriato per il parametro.</span><span class="sxs-lookup"><span data-stu-id="9881e-109">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that has the integer substituted appropriately for its parameter.</span></span> <span data-ttu-id="9881e-110">D'ora in poi, ogni volta che il codice programma usa uno stack di interi, il runtime riutilizzerà la classe <xref:System.Collections.Generic.Stack%601> specializzata generata.</span><span class="sxs-lookup"><span data-stu-id="9881e-110">Now, whenever your program code uses a stack of integers, the runtime reuses the generated specialized <xref:System.Collections.Generic.Stack%601> class.</span></span> <span data-ttu-id="9881e-111">Nell'esempio seguente vengono create due istanze di uno stack di interi che condividono un'istanza singola nel codice `Stack<int>`:</span><span class="sxs-lookup"><span data-stu-id="9881e-111">In the following example, two instances of a stack of integers are created, and they share a single instance of the `Stack<int>` code:</span></span>  
  
 <span data-ttu-id="9881e-112">[!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-112">[!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]</span></span>  
  
 <span data-ttu-id="9881e-113">Tuttavia, si supponga che venga creata un'altra classe <xref:System.Collections.Generic.Stack%601> con un tipo valore diverso, ad esempio `long`, o una struttura definita dall'utente come parametro in un altro punto del codice.</span><span class="sxs-lookup"><span data-stu-id="9881e-113">However, suppose that another <xref:System.Collections.Generic.Stack%601> class with a different value type such as a `long` or a user-defined structure as its parameter is created at another point in your code.</span></span> <span data-ttu-id="9881e-114">Di conseguenza, il runtime genererà un'altra versione del tipo generico e sostituirà un valore `long` nelle posizioni appropriate in MSIL.</span><span class="sxs-lookup"><span data-stu-id="9881e-114">As a result, the runtime generates another version of the generic type and substitutes a `long` in the appropriate locations in MSIL.</span></span> <span data-ttu-id="9881e-115">Le conversioni non sono più necessarie, perché ogni classe generica specializzata contiene il tipo valore in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="9881e-115">Conversions are no longer necessary because each specialized generic class natively contains the value type.</span></span>  
  
 <span data-ttu-id="9881e-116">I generics hanno un funzionamento leggermente diverso con i tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="9881e-116">Generics work somewhat differently for reference types.</span></span> <span data-ttu-id="9881e-117">La prima volta che viene costruito un tipo generico con qualsiasi tipo riferimento, il runtime crea un tipo generico specializzato con riferimenti a oggetti sostituiti per i parametri in MSIL.</span><span class="sxs-lookup"><span data-stu-id="9881e-117">The first time a generic type is constructed with any reference type, the runtime creates a specialized generic type with object references substituted for the parameters in the MSIL.</span></span> <span data-ttu-id="9881e-118">Quindi, ogni volta che viene creata un'istanza di un tipo costruito con un tipo riferimento come parametro, indipendentemente dal tipo, il runtime riutilizza la versione specializzata precedentemente creata del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="9881e-118">Then, every time that a constructed type is instantiated with a reference type as its parameter, regardless of what type it is, the runtime reuses the previously created specialized version of the generic type.</span></span> <span data-ttu-id="9881e-119">Questo è possibile perché tutti i riferimenti hanno le stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9881e-119">This is possible because all references are the same size.</span></span>  
  
 <span data-ttu-id="9881e-120">Ad esempio, si supponga di avere due tipi riferimento, una classe `Customer` e una classe `Order`, e di aver creato uno stack di tipi `Customer`:</span><span class="sxs-lookup"><span data-stu-id="9881e-120">For example, suppose you had two reference types, a `Customer` class and an `Order` class, and also suppose that you created a stack of `Customer` types:</span></span>  
  
 <span data-ttu-id="9881e-121">[!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-121">[!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]</span></span>  
  
 <span data-ttu-id="9881e-122">[!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-122">[!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]</span></span>  
  
 <span data-ttu-id="9881e-123">A questo punto, il runtime genera una versione specializzata della classe <xref:System.Collections.Generic.Stack%601> in cui sono archiviati riferimenti a oggetti che verranno compilati successivamente invece di archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="9881e-123">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that stores object references that will be filled in later instead of storing data.</span></span> <span data-ttu-id="9881e-124">Si supponga che la riga di codice successiva crei uno stack di un altro tipo riferimento, chiamato `Order`:</span><span class="sxs-lookup"><span data-stu-id="9881e-124">Suppose the next line of code creates a stack of another reference type, which is named `Order`:</span></span>  
  
 <span data-ttu-id="9881e-125">[!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-125">[!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]</span></span>  
  
 <span data-ttu-id="9881e-126">Diversamente dai tipi valore, non viene creata un'altra versione specializzata della classe <xref:System.Collections.Generic.Stack%601> per il tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="9881e-126">Unlike with value types, another specialized version of the <xref:System.Collections.Generic.Stack%601> class is not created for the `Order` type.</span></span> <span data-ttu-id="9881e-127">Viene invece creata un'istanza della versione specializzata della classe <xref:System.Collections.Generic.Stack%601> e viene impostata la variabile `orders` per referenziarla.</span><span class="sxs-lookup"><span data-stu-id="9881e-127">Instead, an instance of the specialized version of the <xref:System.Collections.Generic.Stack%601> class is created and the `orders` variable is set to reference it.</span></span> <span data-ttu-id="9881e-128">Si supponga di individuare una riga di codice per la creazione di uno stack di un tipo `Customer`:</span><span class="sxs-lookup"><span data-stu-id="9881e-128">Suppose that you then encountered a line of code to create a stack of a `Customer` type:</span></span>  
  
 <span data-ttu-id="9881e-129">[!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="9881e-129">[!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]</span></span>  
  
 <span data-ttu-id="9881e-130">Come per l'uso precedente della classe <xref:System.Collections.Generic.Stack%601> creata con il tipo `Order`, verrà creata un'altra istanza della classe <xref:System.Collections.Generic.Stack%601> specializzata.</span><span class="sxs-lookup"><span data-stu-id="9881e-130">As with the previous use of the <xref:System.Collections.Generic.Stack%601> class created by using the `Order` type, another instance of the specialized <xref:System.Collections.Generic.Stack%601> class is created.</span></span> <span data-ttu-id="9881e-131">I puntatori contenuti vengono impostati in modo da fare riferimento a un'area di memoria delle dimensioni di un tipo `Customer`.</span><span class="sxs-lookup"><span data-stu-id="9881e-131">The pointers that are contained therein are set to reference an area of memory the size of a `Customer` type.</span></span> <span data-ttu-id="9881e-132">Poiché il numero di tipi riferimento può variare ampiamente a seconda del programma, l'implementazione C# di generics riduce notevolmente la quantità di codice limitando a uno il numero di classi specializzate create dal compilatore per classi generiche di tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="9881e-132">Because the number of reference types can vary wildly from program to program, the C# implementation of generics greatly reduces the amount of code by reducing to one the number of specialized classes created by the compiler for generic classes of reference types.</span></span>  
  
 <span data-ttu-id="9881e-133">Inoltre, quando viene creata un'istanza di una classe C# generica usando un tipo valore o un parametro di tipo riferimento, la reflection può eseguire query sulla classe, accertandone il tipo effettivo e il parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="9881e-133">Moreover, when a generic C# class is instantiated by using a value type or reference type parameter, reflection can query it at runtime and both its actual type and its type parameter can be ascertained.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9881e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9881e-134">See Also</span></span>  
 <span data-ttu-id="9881e-135"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="9881e-135"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="9881e-136">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9881e-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9881e-137">[Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="9881e-137">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="9881e-138">Generics</span><span class="sxs-lookup"><span data-stu-id="9881e-138">Generics</span></span>](~/docs/standard/generics/index.md)

