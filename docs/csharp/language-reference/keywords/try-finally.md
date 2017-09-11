---
title: try...finally (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
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
ms.openlocfilehash: 88b9960b8c026d1fcd8eed1815ade57422cd2a15
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="try-finally-c-reference"></a><span data-ttu-id="62d77-102">try...finally (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="62d77-102">try-finally (C# Reference)</span></span>
<span data-ttu-id="62d77-103">Usando un blocco `finally`, è possibile eliminare le risorse allocate in un blocco [try](../../../csharp/language-reference/keywords/try-catch.md) ed è possibile eseguire codice anche se viene generata un'eccezione di blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="62d77-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](../../../csharp/language-reference/keywords/try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="62d77-104">In genere, le istruzioni di un blocco `finally` vengono eseguite quando il controllo lascia un'istruzione `try`.</span><span class="sxs-lookup"><span data-stu-id="62d77-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="62d77-105">Il trasferimento del controllo può verificarsi come risultato dell'esecuzione normale, dell'esecuzione di un'istruzione `break`, `continue`, `goto` o `return` o della propagazione di un'eccezione dell'istruzione `try`.</span><span class="sxs-lookup"><span data-stu-id="62d77-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>  
  
 <span data-ttu-id="62d77-106">All'interno di un'eccezione gestita, l'esecuzione del blocco `finally` associato è garantita.</span><span class="sxs-lookup"><span data-stu-id="62d77-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="62d77-107">Tuttavia, se l'eccezione non è gestita, l'esecuzione del blocco `finally` dipende da come viene attivata l'operazione di rimozione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="62d77-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="62d77-108">Ciò, a sua volta, dipende da come viene configurato il computer.</span><span class="sxs-lookup"><span data-stu-id="62d77-108">That, in turn, is dependent on how your computer is set up.</span></span> <span data-ttu-id="62d77-109">Per altre informazioni, vedere [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371) (Elaborazione di eccezioni non gestite nel CLR).</span><span class="sxs-lookup"><span data-stu-id="62d77-109">For more information, see [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span></span>  
  
 <span data-ttu-id="62d77-110">In genere, quando un'eccezione non gestita termina un'applicazione non è importante sapere se il blocco `finally` è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62d77-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="62d77-111">Tuttavia, se si dispone di istruzioni in un blocco `finally` che deve essere eseguito anche in questo caso, una soluzione consiste nell'aggiungere un blocco `catch` all'istruzione `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="62d77-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="62d77-112">In alternativa, è possibile intercettare l'eccezione che potrebbe essere generata nel blocco `try` di un'istruzione `try`-`finally` in alto nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="62d77-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="62d77-113">Vale a dire, è possibile intercettare l'eccezione nel metodo che chiama il metodo che contiene l'istruzione `try`-`finally`, nel metodo che chiama questo metodo o in qualsiasi metodo nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="62d77-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="62d77-114">Se non viene rilevata l'eccezione, l'esecuzione del blocco `finally` varia a seconda che il sistema operativo scelga di generare un'operazione di rimozione dell'eccezione o meno.</span><span class="sxs-lookup"><span data-stu-id="62d77-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62d77-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="62d77-115">Example</span></span>  
 <span data-ttu-id="62d77-116">Nell'esempio seguente un'istruzione di conversione non valida causa un'eccezione `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="62d77-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="62d77-117">L'eccezione viene non è gestita.</span><span class="sxs-lookup"><span data-stu-id="62d77-117">The exception is unhandled.</span></span>  
  
 <span data-ttu-id="62d77-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="62d77-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span></span>  
  
 <span data-ttu-id="62d77-119">Nell'esempio seguente viene intercettata un'eccezione del metodo `TryCast` in un metodo nella parte più in alto dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="62d77-119">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>  
  
 <span data-ttu-id="62d77-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="62d77-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="62d77-121">Per altre informazioni su `finally`, vedere [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="62d77-121">For more information about `finally`, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
 <span data-ttu-id="62d77-122">C# contiene anche l'[istruzione using](../../../csharp/language-reference/keywords/using-statement.md), che fornisce funzionalità simili per gli oggetti <xref:System.IDisposable> con una sintassi comoda.</span><span class="sxs-lookup"><span data-stu-id="62d77-122">C# also contains the [using statement](../../../csharp/language-reference/keywords/using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="62d77-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="62d77-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62d77-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d77-124">See Also</span></span>  
 <span data-ttu-id="62d77-125">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="62d77-126">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="62d77-127">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="62d77-128">[Istruzioni try, throw e catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="62d77-128">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="62d77-129">[Istruzioni di gestione delle eccezioni](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-129">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="62d77-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="62d77-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="62d77-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 [<span data-ttu-id="62d77-132">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="62d77-132">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

