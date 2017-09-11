---
title: Metodi anonimi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
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
ms.openlocfilehash: 92842becf26a15ab1a6f5e9621002abf71dc67bc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="6952d-102">Metodi anonimi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6952d-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="6952d-103">Nelle versioni di C# precedenti alla 2.0, l'unico modo per dichiarare un [delegato](../../../csharp/language-reference/keywords/delegate.md) consiste nell'usare [metodi denominati](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6952d-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="6952d-104">In C# 2.0 sono stati introdotti i metodi anonimi e in C# versione 3.0 e successive le espressioni lambda sostituiscono i metodi anonimi come modalità preferita per la scrittura di codice inline.</span><span class="sxs-lookup"><span data-stu-id="6952d-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="6952d-105">Le informazioni sui metodi anonimi in questo argomento, tuttavia, si applicano anche alle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="6952d-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="6952d-106">Esiste un caso in cui un metodo anonimo fornisce funzionalità non disponibili nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="6952d-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="6952d-107">I metodi anonimi consentono di omettere l'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="6952d-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="6952d-108">Ciò significa che un metodo anonimo può essere convertito in delegati con un'ampia gamma di firme.</span><span class="sxs-lookup"><span data-stu-id="6952d-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="6952d-109">Questo non è possibile con le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="6952d-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="6952d-110">Per altre informazioni specifiche sulle espressioni lambda, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6952d-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="6952d-111">La creazione di metodi anonimi è essenzialmente un modo per passare un blocco di codice come un parametro del delegato.</span><span class="sxs-lookup"><span data-stu-id="6952d-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="6952d-112">Di seguito sono riportati due esempi:</span><span class="sxs-lookup"><span data-stu-id="6952d-112">Here are two examples:</span></span>  
  
 <span data-ttu-id="6952d-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6952d-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="6952d-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6952d-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="6952d-115">L'uso dei metodi anonimi consente di ridurre il carico di scrittura del codice correlato alla creazione di istanze dei delegati, perché non è necessario creare un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="6952d-115">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="6952d-116">Specificare un blocco di codice invece di un delegato, ad esempio, può rivelarsi utile in una situazione in cui la creazione di un metodo può sembrare un sovraccarico inutile.</span><span class="sxs-lookup"><span data-stu-id="6952d-116">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="6952d-117">Un buon esempio può essere l'avvio di un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="6952d-117">A good example would be when you start a new thread.</span></span> <span data-ttu-id="6952d-118">Questa classe crea un thread e contiene anche il codice eseguito dal thread senza creare un metodo aggiuntivo per il delegato.</span><span class="sxs-lookup"><span data-stu-id="6952d-118">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 <span data-ttu-id="6952d-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6952d-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6952d-120">Note</span><span class="sxs-lookup"><span data-stu-id="6952d-120">Remarks</span></span>  
 <span data-ttu-id="6952d-121">L'ambito dei parametri di un metodo anonimo è il *blocco del metodo anonimo*.</span><span class="sxs-lookup"><span data-stu-id="6952d-121">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="6952d-122">È errato inserire all'interno del blocco del metodo anonimo un'istruzione di salto come [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), se la destinazione è esterna al blocco.</span><span class="sxs-lookup"><span data-stu-id="6952d-122">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="6952d-123">È un errore anche inserire all'esterno del blocco del metodo anonimo un'istruzione di salto come `goto`, `break` o `continue`, se la destinazione è interna al blocco.</span><span class="sxs-lookup"><span data-stu-id="6952d-123">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="6952d-124">Le variabili e i parametri locali, il cui ambito contiene una dichiarazione di metodo anonimo, sono denominati variabili *esterne* del metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="6952d-124">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="6952d-125">Nel segmento di codice seguente, ad esempio, `n` è una variabile esterna:</span><span class="sxs-lookup"><span data-stu-id="6952d-125">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 <span data-ttu-id="6952d-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6952d-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="6952d-127">Un riferimento alla variabile esterna `n` viene detto *acquisito* al momento della creazione del delegato.</span><span class="sxs-lookup"><span data-stu-id="6952d-127">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="6952d-128">A differenza delle variabili locali, la durata di una variabile acquisita si estende fino a quando i delegati che fanno riferimento ai metodi anonimi sono idonei per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6952d-128">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="6952d-129">Un metodo anonimo non può accedere ai parametri [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md) di un ambito esterno.</span><span class="sxs-lookup"><span data-stu-id="6952d-129">An anonymous method cannot access the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="6952d-130">Nessun codice non gestito è accessibile all'interno di un *blocco di metodo anonimo*.</span><span class="sxs-lookup"><span data-stu-id="6952d-130">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="6952d-131">I metodi anonimi non sono consentiti a sinistra dell'operatore [is](../../../csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="6952d-131">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6952d-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6952d-132">Example</span></span>  
 <span data-ttu-id="6952d-133">L'esempio seguente dimostra due modi per creare un'istanza di un delegato:</span><span class="sxs-lookup"><span data-stu-id="6952d-133">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="6952d-134">Associazione del delegato a un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="6952d-134">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="6952d-135">Associazione del delegato con un metodo denominato (`DoWork`).</span><span class="sxs-lookup"><span data-stu-id="6952d-135">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="6952d-136">In ogni caso, viene visualizzato un messaggio quando viene richiamato il delegato.</span><span class="sxs-lookup"><span data-stu-id="6952d-136">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 <span data-ttu-id="6952d-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="6952d-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6952d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6952d-138">See Also</span></span>  
 <span data-ttu-id="6952d-139">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6952d-140">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6952d-141">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-141">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="6952d-142">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-142">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="6952d-143">[Codice di tipo unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-143">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="6952d-144">[Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="6952d-144">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="6952d-145">Delegati con metodi denominati o metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="6952d-145">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)

