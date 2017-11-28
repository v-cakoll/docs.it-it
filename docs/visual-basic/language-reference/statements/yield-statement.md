---
title: Istruzione Yield (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99f5129d5cb43cddfb17731f337a72fae22d3626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="0cd06-102">Istruzione Yield (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cd06-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="0cd06-103">Invia l'elemento successivo di una raccolta da un `For Each...Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0cd06-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cd06-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cd06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cd06-105">Parameters</span></span>  
  
|<span data-ttu-id="0cd06-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0cd06-106">Term</span></span>|<span data-ttu-id="0cd06-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0cd06-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="0cd06-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0cd06-108">Required.</span></span> <span data-ttu-id="0cd06-109">Un'espressione che è implicitamente convertibile nel tipo della funzione iteratore o `Get` funzione di accesso che contiene il `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0cd06-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cd06-110">Note</span><span class="sxs-lookup"><span data-stu-id="0cd06-110">Remarks</span></span>  
 <span data-ttu-id="0cd06-111">Il `Yield` l'istruzione restituisce un elemento di una raccolta in una fase.</span><span class="sxs-lookup"><span data-stu-id="0cd06-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="0cd06-112">Il `Yield` istruzione è inclusa in una funzione iterator o `Get` della funzione di accesso, a cui eseguire iterazioni personalizzate in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0cd06-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="0cd06-113">Utilizzare una funzione iterator mediante un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="0cd06-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="0cd06-114">Ogni iterazione di `For Each` ciclo chiama la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="0cd06-115">Quando un `Yield` viene raggiunta l'istruzione nella funzione iteratore `expression` viene restituito, e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="0cd06-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="0cd06-116">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="0cd06-117">Deve esistere una conversione implicita dal tipo di `expression` nel `Yield` istruzione per il tipo restituito dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="0cd06-118">È possibile utilizzare un `Exit Function` o `Return` istruzione per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="0cd06-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="0cd06-119">"Yield" non è una parola riservata e ha un significato speciale solo quando è utilizzata in un `Iterator` funzione o `Get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="0cd06-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="0cd06-120">Per ulteriori informazioni sulle funzioni di iteratore e `Get` funzioni di accesso, vedere [iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="0cd06-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="0cd06-121">Funzioni di iteratore e funzioni di accesso Get</span><span class="sxs-lookup"><span data-stu-id="0cd06-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="0cd06-122">La dichiarazione di una funzione iterator o `Get` della funzione di accesso deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cd06-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="0cd06-123">Deve includere un [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="0cd06-124">Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="0cd06-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="0cd06-125">Non può avere qualsiasi `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="0cd06-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="0cd06-126">In un evento, costruttore di istanza, il costruttore statico o distruttore statico non può verificarsi una funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="0cd06-127">Una funzione iteratore può essere una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="0cd06-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="0cd06-128">Per altre informazioni, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="0cd06-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="0cd06-129">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="0cd06-129">Exception Handling</span></span>  
 <span data-ttu-id="0cd06-130">Oggetto `Yield` istruzione può essere presenti in un `Try` blocco di un [provare... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0cd06-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="0cd06-131">Oggetto `Try` blocco che ha un `Yield` istruzione possono essere presenti `Catch` blocchi e può avere un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="0cd06-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="0cd06-132">Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="0cd06-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="0cd06-133">Se il `For Each` corpo (all'esterno della funzione di iteratore) genera un'eccezione, un `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` blocco nella funzione iteratore viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0cd06-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="0cd06-134">Oggetto `Catch` blocco all'interno di una funzione iterator intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="0cd06-135">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="0cd06-135">Technical Implementation</span></span>  
 <span data-ttu-id="0cd06-136">Il codice seguente restituisce un `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi del `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="0cd06-137">La chiamata a `MyIteratorFunction` non esegue il corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="0cd06-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="0cd06-138">La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="0cd06-139">In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="0cd06-140">Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva.</span><span class="sxs-lookup"><span data-stu-id="0cd06-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="0cd06-141">Il `Yield` l'istruzione restituisce un'espressione che determina non solo il valore della `element` variabile per l'utilizzo dal corpo del ciclo, ma anche il <xref:System.Collections.Generic.IEnumerator%601.Current%2A> proprietà degli elementi, ovvero un `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="0cd06-142">In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="0cd06-143">Il `For Each` ciclo viene completato quando la fine della funzione iteratore o un `Return` o `Exit Function` viene raggiunta l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0cd06-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cd06-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="0cd06-144">Example</span></span>  
 <span data-ttu-id="0cd06-145">Nell'esempio seguente è presente un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="0cd06-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="0cd06-146">Ogni iterazione del [per ogni](../../../visual-basic/language-reference/statements/for-each-next-statement.md) corpo dell'istruzione in `Main` crea una chiamata al `Power` funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="0cd06-147">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="0cd06-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="0cd06-148">Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601>, un tipo interfaccia iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="0cd06-149">Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.</span><span class="sxs-lookup"><span data-stu-id="0cd06-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="0cd06-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="0cd06-150">Example</span></span>  
 <span data-ttu-id="0cd06-151">Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="0cd06-152">La dichiarazione di proprietà include un `Iterator` modificatore.</span><span class="sxs-lookup"><span data-stu-id="0cd06-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="0cd06-153">Per ulteriori esempi, vedere [iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="0cd06-153">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd06-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cd06-154">See Also</span></span>  
 [<span data-ttu-id="0cd06-155">Iteratori</span><span class="sxs-lookup"><span data-stu-id="0cd06-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="0cd06-156">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="0cd06-156">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
