---
title: Delegati (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 516f5193509d3c87cc8fb7a36e2d69e04a85a6b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335281"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="3f020-102">Delegati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3f020-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="3f020-103">Un [delegate](../../../csharp/language-reference/keywords/delegate.md) è un tipo che rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari.</span><span class="sxs-lookup"><span data-stu-id="3f020-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="3f020-104">Quando si crea un'istanza di un delegato, è possibile associare l'istanza a qualsiasi metodo con una firma compatibile e un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="3f020-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="3f020-105">Tramite l'istanza di delegato è possibile richiamare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="3f020-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="3f020-106">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="3f020-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="3f020-107">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="3f020-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="3f020-108">Creare un metodo personalizzato e una classe, ad esempio un controllo Windows, che può chiamare tale metodo quando si verifica un determinato evento.</span><span class="sxs-lookup"><span data-stu-id="3f020-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="3f020-109">Nell'esempio che segue viene illustrata la dichiarazione di un delegato:</span><span class="sxs-lookup"><span data-stu-id="3f020-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="3f020-110">Qualsiasi metodo di qualsiasi classe o struct accessibile che corrisponde al tipo di delegato può essere assegnato al delegato.</span><span class="sxs-lookup"><span data-stu-id="3f020-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="3f020-111">Il metodo può essere un metodo statico o di istanza.</span><span class="sxs-lookup"><span data-stu-id="3f020-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="3f020-112">In questo modo è possibile modificare le chiamate ai metodi a livello di codice, nonché inserire nuovo codice nelle classi esistenti.</span><span class="sxs-lookup"><span data-stu-id="3f020-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f020-113">Nel contesto di overload dei metodi, la firma di un metodo non include il valore restituito,</span><span class="sxs-lookup"><span data-stu-id="3f020-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="3f020-114">mentre nel contesto dei delegati, la firma include il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3f020-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="3f020-115">In altre parole, un metodo deve restituire lo stesso tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="3f020-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="3f020-116">La possibilità di fare riferimento a un metodo come parametro rende i delegati ideali per la definizione di metodi di callback.</span><span class="sxs-lookup"><span data-stu-id="3f020-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="3f020-117">È ad esempio possibile passare un riferimento a un metodo per il confronto di due oggetti passati come argomento a un algoritmo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="3f020-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="3f020-118">Poiché il codice di confronto è in una routine separata, l'algoritmo di ordinamento può essere scritto in modo più generale.</span><span class="sxs-lookup"><span data-stu-id="3f020-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="3f020-119">Panoramica dei delegati</span><span class="sxs-lookup"><span data-stu-id="3f020-119">Delegates Overview</span></span>  
 <span data-ttu-id="3f020-120">Di seguito sono riportate le proprietà dei delegati:</span><span class="sxs-lookup"><span data-stu-id="3f020-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="3f020-121">Sono simili ai puntatori a funzione del linguaggio C++, ma sono indipendenti dai tipi.</span><span class="sxs-lookup"><span data-stu-id="3f020-121">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="3f020-122">Consentono di passare metodi come parametri.</span><span class="sxs-lookup"><span data-stu-id="3f020-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="3f020-123">Possono essere utilizzati per definire metodi di callback.</span><span class="sxs-lookup"><span data-stu-id="3f020-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="3f020-124">Possono essere concatenati, ad esempio per chiamare più metodi su un singolo evento.</span><span class="sxs-lookup"><span data-stu-id="3f020-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="3f020-125">Non devono corrispondere necessariamente al tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="3f020-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="3f020-126">Per altre informazioni, vedere [Uso della varianza nei delegati](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="3f020-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="3f020-127">In C# versione 2.0 sono stati introdotti i [metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) che consentono di passare blocchi di codice come parametri anziché un metodo definito separato.</span><span class="sxs-lookup"><span data-stu-id="3f020-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="3f020-128">In C# 3.0 sono state introdotte le espressioni lambda per scrivere in modo più conciso i blocchi di codice in linea.</span><span class="sxs-lookup"><span data-stu-id="3f020-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="3f020-129">I metodi anonimi e le espressioni lambda vengono compilati, in determinati contesti, in tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="3f020-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="3f020-130">Queste funzionalità sono ora note complessivamente come funzioni anonime.</span><span class="sxs-lookup"><span data-stu-id="3f020-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="3f020-131">Per altre informazioni sulle espressioni lambda, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="3f020-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f020-132">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3f020-132">In This Section</span></span>  
  
-   [<span data-ttu-id="3f020-133">Uso dei delegati</span><span class="sxs-lookup"><span data-stu-id="3f020-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="3f020-134">Quando utilizzare i delegati anziché le interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3f020-134">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/library/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="3f020-135">Delegati con metodi denominati o metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="3f020-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="3f020-136">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="3f020-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="3f020-137">Uso della varianza nei delegati</span><span class="sxs-lookup"><span data-stu-id="3f020-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="3f020-138">Procedura: Combinare delegati multicast</span><span class="sxs-lookup"><span data-stu-id="3f020-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="3f020-139">Procedura: Dichiarare un delegato, crearne un'istanza e usarlo</span><span class="sxs-lookup"><span data-stu-id="3f020-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="3f020-140">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3f020-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="3f020-141">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="3f020-141">Featured Book Chapters</span></span>  
 <span data-ttu-id="3f020-142">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f020-142">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="3f020-143">[Delegati ed eventi](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f020-143">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f020-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f020-144">See Also</span></span>  
 <xref:System.Delegate>  
 [<span data-ttu-id="3f020-145">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3f020-145">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3f020-146">Eventi</span><span class="sxs-lookup"><span data-stu-id="3f020-146">Events</span></span>](../../../csharp/programming-guide/events/index.md)
