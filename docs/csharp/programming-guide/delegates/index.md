---
title: Delegati (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
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
ms.openlocfilehash: 1d3dc2252b086f9df9e64a059a53ec8792e11b45
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="e7f5e-102">Delegati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e7f5e-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="e7f5e-103">Un [delegate](../../../csharp/language-reference/keywords/delegate.md) è un tipo che rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="e7f5e-104">Quando si crea un'istanza di un delegato, è possibile associare l'istanza a qualsiasi metodo con una firma compatibile e un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="e7f5e-105">Tramite l'istanza di delegato è possibile richiamare (o chiamare) il metodo.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="e7f5e-106">I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="e7f5e-107">I gestori di evento non sono altro che metodi richiamati tramite delegati.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="e7f5e-108">Creare un metodo personalizzato e una classe, ad esempio un controllo Windows, che può chiamare tale metodo quando si verifica un determinato evento.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="e7f5e-109">Nell'esempio che segue viene illustrata la dichiarazione di un delegato:</span><span class="sxs-lookup"><span data-stu-id="e7f5e-109">The following example shows a delegate declaration:</span></span>  
  
 <span data-ttu-id="e7f5e-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7f5e-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="e7f5e-111">Qualsiasi metodo di qualsiasi classe o struct accessibile che corrisponde al tipo di delegato può essere assegnato al delegato.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-111">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="e7f5e-112">Il metodo può essere un metodo statico o di istanza.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-112">The method can be either static or an instance method.</span></span> <span data-ttu-id="e7f5e-113">In questo modo è possibile modificare le chiamate ai metodi a livello di codice, nonché inserire nuovo codice nelle classi esistenti.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-113">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7f5e-114">Nel contesto di overload dei metodi, la firma di un metodo non include il valore restituito,</span><span class="sxs-lookup"><span data-stu-id="e7f5e-114">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="e7f5e-115">mentre nel contesto dei delegati, la firma include il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-115">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="e7f5e-116">In altre parole, un metodo deve restituire lo stesso tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-116">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="e7f5e-117">La possibilità di fare riferimento a un metodo come parametro rende i delegati ideali per la definizione di metodi di callback.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-117">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="e7f5e-118">È ad esempio possibile passare un riferimento a un metodo per il confronto di due oggetti passati come argomento a un algoritmo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-118">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="e7f5e-119">Poiché il codice di confronto è in una routine separata, l'algoritmo di ordinamento può essere scritto in modo più generale.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-119">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="e7f5e-120">Panoramica dei delegati</span><span class="sxs-lookup"><span data-stu-id="e7f5e-120">Delegates Overview</span></span>  
 <span data-ttu-id="e7f5e-121">Di seguito sono riportate le proprietà dei delegati:</span><span class="sxs-lookup"><span data-stu-id="e7f5e-121">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="e7f5e-122">Sono simili ai puntatori a funzione del linguaggio C++, ma sono indipendenti dai tipi.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-122">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="e7f5e-123">Consentono di passare metodi come parametri.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-123">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="e7f5e-124">Possono essere utilizzati per definire metodi di callback.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-124">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="e7f5e-125">Possono essere concatenati, ad esempio per chiamare più metodi su un singolo evento.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-125">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="e7f5e-126">Non devono corrispondere necessariamente al tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-126">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="e7f5e-127">Per altre informazioni, vedere [Uso della varianza nei delegati](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5e-127">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="e7f5e-128">In C# versione 2.0 sono stati introdotti i [metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) che consentono di passare blocchi di codice come parametri anziché un metodo definito separato.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-128">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="e7f5e-129">In C# 3.0 sono state introdotte le espressioni lambda per scrivere in modo più conciso i blocchi di codice in linea.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-129">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="e7f5e-130">I metodi anonimi e le espressioni lambda vengono compilati, in determinati contesti, in tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-130">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="e7f5e-131">Queste funzionalità sono ora note complessivamente come funzioni anonime.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-131">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="e7f5e-132">Per altre informazioni sulle espressioni lambda, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5e-132">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7f5e-133">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e7f5e-133">In This Section</span></span>  
  
-   [<span data-ttu-id="e7f5e-134">Uso dei delegati</span><span class="sxs-lookup"><span data-stu-id="e7f5e-134">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="e7f5e-135">Quando utilizzare i delegati anziché le interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e7f5e-135">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="e7f5e-136">Delegati con metodi denominati o metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="e7f5e-136">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="e7f5e-137">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="e7f5e-137">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="e7f5e-138">Uso della varianza nei delegati</span><span class="sxs-lookup"><span data-stu-id="e7f5e-138">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="e7f5e-139">Procedura: Combinare delegati multicast</span><span class="sxs-lookup"><span data-stu-id="e7f5e-139">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="e7f5e-140">Procedura: Dichiarare un delegato, crearne un'istanza e usarlo</span><span class="sxs-lookup"><span data-stu-id="e7f5e-140">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="e7f5e-141">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e7f5e-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="e7f5e-142">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="e7f5e-142">Featured Book Chapters</span></span>  
 <span data-ttu-id="e7f5e-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="e7f5e-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="e7f5e-144">[Delegati ed eventi](http://go.microsoft.com/fwlink/?LinkId=195418) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="e7f5e-144">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f5e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7f5e-145">See Also</span></span>  
 <span data-ttu-id="e7f5e-146"><xref:System.Delegate></span><span class="sxs-lookup"><span data-stu-id="e7f5e-146"><xref:System.Delegate></span></span>   
 <span data-ttu-id="e7f5e-147">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7f5e-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e7f5e-148">Eventi</span><span class="sxs-lookup"><span data-stu-id="e7f5e-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)

