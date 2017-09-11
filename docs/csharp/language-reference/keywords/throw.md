---
title: throw (Riferimenti per C#)
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a><span data-ttu-id="28ae4-102">throw (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="28ae4-102">throw (C# Reference)</span></span>
<span data-ttu-id="28ae4-103">Segnala l'occorrenza di un'eccezione durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="28ae4-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28ae4-104">Note</span><span class="sxs-lookup"><span data-stu-id="28ae4-104">Remarks</span></span>

<span data-ttu-id="28ae4-105">La sintassi di `throw` è:</span><span class="sxs-lookup"><span data-stu-id="28ae4-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="28ae4-106">dove `e` è un'istanza di una classe derivata da <xref:System.Exception?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="28ae4-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=fullName>.</span></span> <span data-ttu-id="28ae4-107">Nell'esempio seguente l'istruzione `throw` viene usata per generare una @System.IndexOutOfRangeException, se l'argomento passato a un metodo denominato `GetNumber` non corrisponde a un indice valido di una matrice interna.</span><span class="sxs-lookup"><span data-stu-id="28ae4-107">The following example uses the `throw` statement to throw an @System.IndexOutOfRangeException if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

<span data-ttu-id="28ae4-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span></span>  

<span data-ttu-id="28ae4-109">I caller al metodo usano quindi un blocco `try-catch` o `try-catch-finally` per gestire l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="28ae4-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="28ae4-110">L'esempio seguente gestisce l'eccezione generata dal metodo `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="28ae4-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

<span data-ttu-id="28ae4-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span></span>  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="28ae4-112">Nuova generazione di un'eccezione</span><span class="sxs-lookup"><span data-stu-id="28ae4-112">Re-throwing an exception</span></span>

<span data-ttu-id="28ae4-113">È possibile anche usare `throw` in un blocco `catch` per generare nuovamente un'eccezione gestita in un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="28ae4-113">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="28ae4-114">In questo caso, `throw` non accetta un operando di eccezione.</span><span class="sxs-lookup"><span data-stu-id="28ae4-114">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="28ae4-115">È particolarmente utile quando un metodo passa un argomento da un caller a un altro metodo di raccolta e il metodo di raccolta genera un'eccezione che deve essere passata al caller.</span><span class="sxs-lookup"><span data-stu-id="28ae4-115">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="28ae4-116">Nell'esempio seguente viene generata nuovamente una @System.NullReferenceException, che viene generata quando si tenta di recuperare il primo carattere di una stringa non inizializzata.</span><span class="sxs-lookup"><span data-stu-id="28ae4-116">For example, the following example re-throws an @System.NullReferenceException that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

<span data-ttu-id="28ae4-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="28ae4-118">È possibile anche usare la sintassi `throw e` in un blocco `catch` per creare un'istanza di una nuova eccezione da passare al caller.</span><span class="sxs-lookup"><span data-stu-id="28ae4-118">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="28ae4-119">In questo caso non viene mantenuta la traccia dello stack dell'eccezione originale, che è disponibile dalla proprietà @System.Exception.Stacktrace.</span><span class="sxs-lookup"><span data-stu-id="28ae4-119">In this case, the stack trace of the original exception, which is available from the @System.Exception.Stacktrace property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="28ae4-120">Espressione `throw`</span><span class="sxs-lookup"><span data-stu-id="28ae4-120">The `throw` expression</span></span>

<span data-ttu-id="28ae4-121">A partire da C# 7 è possibile usare `throw` come espressione e come istruzione.</span><span class="sxs-lookup"><span data-stu-id="28ae4-121">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="28ae4-122">Ciò consente di generare un'eccezione in contesti non supportati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="28ae4-122">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="28ae4-123">Sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="28ae4-123">These include:</span></span>

- <span data-ttu-id="28ae4-124">[L'operatore condizionale](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28ae4-124">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="28ae4-125">Nell'esempio seguente viene usata un'espressione `throw` per generare una @System.ArgumentException se a un metodo viene passato una matrice di stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="28ae4-125">The following example uses a `throw` expression to throw an @System.ArgumentException if a method is passed an empty string array.</span></span> <span data-ttu-id="28ae4-126">Prima di C# 7, la logica avrebbe dovuto usare un'istruzione `if` / `else`.</span><span class="sxs-lookup"><span data-stu-id="28ae4-126">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   <span data-ttu-id="28ae4-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span></span>  
  
- <span data-ttu-id="28ae4-128">[L'operatore null-coalescing](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28ae4-128">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="28ae4-129">Nell'esempio seguente viene usata un'espressione `throw` con un operatore null-coalescing per generare un'eccezione, se la stringa assegnata a una proprietà `Name` è `null`.</span><span class="sxs-lookup"><span data-stu-id="28ae4-129">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   <span data-ttu-id="28ae4-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span></span>  
 
- <span data-ttu-id="28ae4-131">[lambda](../../lambda-expressions.md) o metodo con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="28ae4-131">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="28ae4-132">L'esempio seguente illustra un metodo con corpo di espressione che genera una @System.InvalidCastException perché non è supportata una conversione in un valore @System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="28ae4-132">The following example illustrates an expression-bodied method that throws an @System.InvalidCastException because a conversion to a @System.DateTime value is not supported.</span></span>
 
   <span data-ttu-id="28ae4-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="28ae4-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span></span>  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="28ae4-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="28ae4-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28ae4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28ae4-135">See Also</span></span>  
 <span data-ttu-id="28ae4-136">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="28ae4-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="28ae4-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="28ae4-139">[Istruzioni try, catch e throw in C++](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-139">[The try, catch, and throw Statements in C++](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="28ae4-140">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="28ae4-141">[Istruzioni di gestione delle eccezioni](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="28ae4-141">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 [<span data-ttu-id="28ae4-142">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="28ae4-142">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

