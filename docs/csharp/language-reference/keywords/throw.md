---
title: throw (Riferimenti per C#)
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 319a4df6f52768cf256c0ad92ca65607b99ce32c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="throw-c-reference"></a><span data-ttu-id="2e387-102">throw (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2e387-102">throw (C# Reference)</span></span>
<span data-ttu-id="2e387-103">Segnala l'occorrenza di un'eccezione durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="2e387-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e387-104">Note</span><span class="sxs-lookup"><span data-stu-id="2e387-104">Remarks</span></span>

<span data-ttu-id="2e387-105">La sintassi di `throw` è:</span><span class="sxs-lookup"><span data-stu-id="2e387-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="2e387-106">dove `e` è un'istanza di una classe derivata da <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e387-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2e387-107">Nell'esempio seguente l'istruzione `throw` viene usata per generare una <xref:System.IndexOutOfRangeException>, se l'argomento passato a un metodo denominato `GetNumber` non corrisponde a un indice valido di una matrice interna.</span><span class="sxs-lookup"><span data-stu-id="2e387-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="2e387-108">I caller al metodo usano quindi un blocco `try-catch` o `try-catch-finally` per gestire l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="2e387-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="2e387-109">L'esempio seguente gestisce l'eccezione generata dal metodo `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="2e387-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="2e387-110">Nuova generazione di un'eccezione</span><span class="sxs-lookup"><span data-stu-id="2e387-110">Re-throwing an exception</span></span>

<span data-ttu-id="2e387-111">È possibile anche usare `throw` in un blocco `catch` per generare nuovamente un'eccezione gestita in un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="2e387-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="2e387-112">In questo caso, `throw` non accetta un operando di eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e387-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="2e387-113">È particolarmente utile quando un metodo passa un argomento da un caller a un altro metodo di raccolta e il metodo di raccolta genera un'eccezione che deve essere passata al caller.</span><span class="sxs-lookup"><span data-stu-id="2e387-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="2e387-114">Nell'esempio seguente viene generata nuovamente una <xref:System.NullReferenceException>, che viene generata quando si tenta di recuperare il primo carattere di una stringa non inizializzata.</span><span class="sxs-lookup"><span data-stu-id="2e387-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="2e387-115">È possibile anche usare la sintassi `throw e` in un blocco `catch` per creare un'istanza di una nuova eccezione da passare al caller.</span><span class="sxs-lookup"><span data-stu-id="2e387-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="2e387-116">In questo caso non viene mantenuta la traccia dello stack dell'eccezione originale, che è disponibile dalla proprietà <xref:System.Exception.StackTrace>.</span><span class="sxs-lookup"><span data-stu-id="2e387-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="2e387-117">Espressione `throw`</span><span class="sxs-lookup"><span data-stu-id="2e387-117">The `throw` expression</span></span>

<span data-ttu-id="2e387-118">A partire da C# 7.0 è possibile usare `throw` come espressione e come istruzione.</span><span class="sxs-lookup"><span data-stu-id="2e387-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="2e387-119">Ciò consente di generare un'eccezione in contesti non supportati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e387-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="2e387-120">Sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="2e387-120">These include:</span></span>

- <span data-ttu-id="2e387-121">[L'operatore condizionale](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2e387-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="2e387-122">Nell'esempio seguente viene usata un'espressione `throw` per generare una <xref:System.ArgumentException> se a un metodo viene passato una matrice di stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="2e387-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="2e387-123">Prima di C# 7.0, la logica avrebbe dovuto usare un'istruzione `if` / `else`.</span><span class="sxs-lookup"><span data-stu-id="2e387-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="2e387-124">[L'operatore null-coalescing](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2e387-124">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="2e387-125">Nell'esempio seguente viene usata un'espressione `throw` con un operatore null-coalescing per generare un'eccezione, se la stringa assegnata a una proprietà `Name` è `null`.</span><span class="sxs-lookup"><span data-stu-id="2e387-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- <span data-ttu-id="2e387-126">[lambda](../../lambda-expressions.md) o metodo con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="2e387-126">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="2e387-127">L'esempio seguente illustra un metodo con corpo di espressione che genera una <xref:System.InvalidCastException> perché non è supportata una conversione in un valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="2e387-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="2e387-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2e387-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e387-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e387-129">See Also</span></span>  
 [<span data-ttu-id="2e387-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2e387-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2e387-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2e387-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2e387-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="2e387-132">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="2e387-133">Istruzioni try, catch e throw in C++</span><span class="sxs-lookup"><span data-stu-id="2e387-133">The try, catch, and throw Statements in C++</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="2e387-134">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2e387-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2e387-135">Istruzioni di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="2e387-135">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="2e387-136">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="2e387-136">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
