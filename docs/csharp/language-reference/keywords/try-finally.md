---
title: try...finally (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 227c880aab89d0ada4431dc50148c36ce00cfda8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155158"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="88eda-102">try...finally (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="88eda-102">try-finally (C# Reference)</span></span>

<span data-ttu-id="88eda-103">Usando un blocco `finally`, è possibile eliminare le risorse allocate in un blocco [try](try-catch.md) ed è possibile eseguire codice anche se viene generata un'eccezione di blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="88eda-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="88eda-104">In genere, le istruzioni di un blocco `finally` vengono eseguite quando il controllo lascia un'istruzione `try`.</span><span class="sxs-lookup"><span data-stu-id="88eda-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="88eda-105">Il trasferimento del controllo può verificarsi come risultato dell'esecuzione normale, dell'esecuzione di un'istruzione `break`, `continue`, `goto` o `return` o della propagazione di un'eccezione dell'istruzione `try`.</span><span class="sxs-lookup"><span data-stu-id="88eda-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="88eda-106">All'interno di un'eccezione gestita, l'esecuzione del blocco `finally` associato è garantita.</span><span class="sxs-lookup"><span data-stu-id="88eda-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="88eda-107">Tuttavia, se l'eccezione non è gestita, l'esecuzione del blocco `finally` dipende da come viene attivata l'operazione di rimozione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="88eda-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="88eda-108">Ciò, a sua volta, dipende da come viene configurato il computer.</span><span class="sxs-lookup"><span data-stu-id="88eda-108">That, in turn, is dependent on how your computer is set up.</span></span>

<span data-ttu-id="88eda-109">In genere, quando un'eccezione non gestita termina un'applicazione non è importante sapere se il blocco `finally` è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="88eda-109">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="88eda-110">Tuttavia, se si dispone di istruzioni in un blocco `finally` che deve essere eseguito anche in questo caso, una soluzione consiste nell'aggiungere un blocco `catch` all'istruzione `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="88eda-110">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="88eda-111">In alternativa, è possibile intercettare l'eccezione che potrebbe essere generata nel blocco `try` di un'istruzione `try`-`finally` in alto nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="88eda-111">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="88eda-112">Vale a dire, è possibile intercettare l'eccezione nel metodo che chiama il metodo che contiene l'istruzione `try`-`finally`, nel metodo che chiama questo metodo o in qualsiasi metodo nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="88eda-112">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="88eda-113">Se non viene rilevata l'eccezione, l'esecuzione del blocco `finally` varia a seconda che il sistema operativo scelga di generare un'operazione di rimozione dell'eccezione o meno.</span><span class="sxs-lookup"><span data-stu-id="88eda-113">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="88eda-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="88eda-114">Example</span></span>

<span data-ttu-id="88eda-115">Nell'esempio seguente un'istruzione di conversione non valida causa un'eccezione `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="88eda-115">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="88eda-116">L'eccezione viene non è gestita.</span><span class="sxs-lookup"><span data-stu-id="88eda-116">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="88eda-117">Nell'esempio seguente viene intercettata un'eccezione del metodo `TryCast` in un metodo nella parte più in alto dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="88eda-117">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="88eda-118">Per altre informazioni su `finally`, vedere [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="88eda-118">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="88eda-119">C# contiene anche l'[istruzione using](using-statement.md), che fornisce funzionalità simili per gli oggetti <xref:System.IDisposable> con una sintassi comoda.</span><span class="sxs-lookup"><span data-stu-id="88eda-119">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="88eda-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="88eda-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="88eda-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88eda-121">See Also</span></span>

- [<span data-ttu-id="88eda-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="88eda-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="88eda-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="88eda-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="88eda-124">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="88eda-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="88eda-125">Istruzioni try, throw e catch (C++)</span><span class="sxs-lookup"><span data-stu-id="88eda-125">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="88eda-126">Istruzioni di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="88eda-126">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="88eda-127">throw</span><span class="sxs-lookup"><span data-stu-id="88eda-127">throw</span></span>](throw.md)
- [<span data-ttu-id="88eda-128">try-catch</span><span class="sxs-lookup"><span data-stu-id="88eda-128">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="88eda-129">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="88eda-129">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)