---
title: Differenze tra modelli C++ e generics C# (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aea1b51c26a8f3de56ea66b9cf89e75bfeb59d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a><span data-ttu-id="79a77-102">Differenze tra modelli C++ e generics C# (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="79a77-102">Differences Between C++ Templates and C# Generics (C# Programming Guide)</span></span>
<span data-ttu-id="79a77-103">I generics C# e i modelli C++ sono entrambi funzionalità del linguaggio che offrono il supporto per i tipi con parametri.</span><span class="sxs-lookup"><span data-stu-id="79a77-103">C# Generics and C++ templates are both language features that provide support for parameterized types.</span></span> <span data-ttu-id="79a77-104">Esistono tuttavia numerose differenze tra queste due funzionalità.</span><span class="sxs-lookup"><span data-stu-id="79a77-104">However, there are many differences between the two.</span></span> <span data-ttu-id="79a77-105">A livello di sintassi, i generics C# rappresentano un approccio più semplice ai tipi con parametri, senza la complessità dei modelli C++.</span><span class="sxs-lookup"><span data-stu-id="79a77-105">At the syntax level, C# generics are a simpler approach to parameterized types without the complexity of C++ templates.</span></span> <span data-ttu-id="79a77-106">Inoltre, il linguaggio C# non è stato concepito per offrire tutte le funzionalità dei modelli C++.</span><span class="sxs-lookup"><span data-stu-id="79a77-106">In addition, C# does not attempt to provide all of the functionality that C++ templates provide.</span></span> <span data-ttu-id="79a77-107">A livello di implementazione, la differenza principale consiste nel fatto che le sostituzioni di tipi generici C# vengono eseguite durante il runtime e, di conseguenza, le informazioni sui tipi generici vengono mantenute per gli oggetti di cui viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="79a77-107">At the implementation level, the primary difference is that C# generic type substitutions are performed at runtime and generic type information is thereby preserved for instantiated objects.</span></span> <span data-ttu-id="79a77-108">Per altre informazioni, vedere [Generics nel runtime](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="79a77-108">For more information, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="79a77-109">Di seguito sono riportate le differenze principali tra generics C# e modelli C++:</span><span class="sxs-lookup"><span data-stu-id="79a77-109">The following are the key differences between C# Generics and C++ templates:</span></span>  
  
-   <span data-ttu-id="79a77-110">I generics C# non offrono lo stesso livello di flessibilità dei modelli C++.</span><span class="sxs-lookup"><span data-stu-id="79a77-110">C# generics do not provide the same amount of flexibility as C++ templates.</span></span> <span data-ttu-id="79a77-111">Ad esempio non è possibile chiamare operatori aritmetici in una classe generica C#, anche se è possibile chiamare operatori definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="79a77-111">For example, it is not possible to call arithmetic operators in a C# generic class, although it is possible to call user defined operators.</span></span>  
  
-   <span data-ttu-id="79a77-112">C# non consente di usare parametri di modello non di tipo, ad esempio `template C<int i> {}`.</span><span class="sxs-lookup"><span data-stu-id="79a77-112">C# does not allow non-type template parameters, such as `template C<int i> {}`.</span></span>  
  
-   <span data-ttu-id="79a77-113">C# non supporta la specializzazione esplicita, ovvero un'implementazione personalizzata di un modello per un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="79a77-113">C# does not support explicit specialization; that is, a custom implementation of a template for a specific type.</span></span>  
  
-   <span data-ttu-id="79a77-114">C# non supporta la specializzazione parziale, ovvero un'implementazione personalizzata per un subset degli argomenti del tipo.</span><span class="sxs-lookup"><span data-stu-id="79a77-114">C# does not support partial specialization: a custom implementation for a subset of the type arguments.</span></span>  
  
-   <span data-ttu-id="79a77-115">C# non consente l'uso del parametro di tipo come classe base per il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="79a77-115">C# does not allow the type parameter to be used as the base class for the generic type.</span></span>  
  
-   <span data-ttu-id="79a77-116">C# non consente l'uso di tipi predefiniti per i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="79a77-116">C# does not allow type parameters to have default types.</span></span>  
  
-   <span data-ttu-id="79a77-117">In C# un parametro di tipo generico non può essere di per sé un elemento generico, anche se i tipi costruiti possono essere usati come generics.</span><span class="sxs-lookup"><span data-stu-id="79a77-117">In C#, a generic type parameter cannot itself be a generic, although constructed types can be used as generics.</span></span> <span data-ttu-id="79a77-118">C++ non consente l'uso di parametri di modello.</span><span class="sxs-lookup"><span data-stu-id="79a77-118">C++ does allow template parameters.</span></span>  
  
-   <span data-ttu-id="79a77-119">C++ consente di usare codice che potrebbe non essere valido per tutti i parametri di tipo nel modello, che viene quindi controllato per verificare la disponibilità del tipo specifico usato come parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="79a77-119">C++ allows code that might not be valid for all type parameters in the template, which is then checked for the specific type used as the type parameter.</span></span> <span data-ttu-id="79a77-120">In C# il codice di una classe deve essere scritto in modo da funzionare con qualsiasi tipo in grado di soddisfare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="79a77-120">C# requires code in a class to be written in such a way that it will work with any type that satisfies the constraints.</span></span> <span data-ttu-id="79a77-121">Ad esempio, in C++ è possibile scrivere una funzione che usa gli operatori aritmetici `+` e `-` sugli oggetti del parametro di tipo, generando un errore al momento della creazione di un'istanza del modello con un tipo che non supporta gli operatori.</span><span class="sxs-lookup"><span data-stu-id="79a77-121">For example, in C++ it is possible to write a function that uses the arithmetic operators `+` and `-` on objects of the type parameter, which will produce an error at the time of instantiation of the template with a type that does not support these operators.</span></span> <span data-ttu-id="79a77-122">In C# questo non è possibile. Gli unici costrutti di linguaggio ammessi sono quelli deducibili dai vincoli.</span><span class="sxs-lookup"><span data-stu-id="79a77-122">C# disallows this; the only language constructs allowed are those that can be deduced from the constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a77-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79a77-123">See Also</span></span>  
 [<span data-ttu-id="79a77-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="79a77-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79a77-125">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="79a77-125">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="79a77-126">Modelli</span><span class="sxs-lookup"><span data-stu-id="79a77-126">Templates</span></span>](/cpp/cpp/templates-cpp)
