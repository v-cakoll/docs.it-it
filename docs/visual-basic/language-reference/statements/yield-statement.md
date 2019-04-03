---
title: Istruzione Yield (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: fea91731694f18625e43c5545b353851e72234a6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821088"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="9eed3-102">Istruzione Yield (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eed3-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="9eed3-103">Invia l'elemento avanti di una raccolta a un `For Each...Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9eed3-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eed3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9eed3-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eed3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9eed3-105">Parameters</span></span>  
  
|<span data-ttu-id="9eed3-106">Termine</span><span class="sxs-lookup"><span data-stu-id="9eed3-106">Term</span></span>|<span data-ttu-id="9eed3-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9eed3-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="9eed3-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9eed3-108">Required.</span></span> <span data-ttu-id="9eed3-109">Un'espressione che è implicitamente convertibile nel tipo di funzione iteratore o `Get` funzione di accesso che contiene il `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9eed3-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9eed3-110">Note</span><span class="sxs-lookup"><span data-stu-id="9eed3-110">Remarks</span></span>  
 <span data-ttu-id="9eed3-111">Il `Yield` istruzione restituisce un elemento di una raccolta in una fase.</span><span class="sxs-lookup"><span data-stu-id="9eed3-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="9eed3-112">Il `Yield` istruzione è inclusa in una funzione iteratore o `Get` della funzione di accesso, a cui eseguire iterazioni personalizzate in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9eed3-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="9eed3-113">Utilizzare una funzione iteratore mediante un [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="9eed3-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="9eed3-114">Ogni iterazione del `For Each` loop chiama la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="9eed3-115">Quando un `Yield` viene raggiunta l'istruzione nella funzione iteratore, `expression` viene restituito, e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="9eed3-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="9eed3-116">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="9eed3-117">Deve esistere una conversione implicita dal tipo della `expression` nella `Yield` istruzione per il tipo restituito dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="9eed3-118">È possibile usare un `Exit Function` o `Return` istruzione per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="9eed3-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="9eed3-119">"Yield" non è una parola riservata e ha un significato speciale solo quando viene usata in un' `Iterator` funzione o `Get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="9eed3-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="9eed3-120">Per altre informazioni sulle funzioni di iteratore e `Get` funzioni di accesso, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="9eed3-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="9eed3-121">Funzioni di iteratore e funzioni di accesso Get</span><span class="sxs-lookup"><span data-stu-id="9eed3-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="9eed3-122">La dichiarazione di una funzione iteratore o `Get` della funzione di accesso deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9eed3-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="9eed3-123">Deve includere un' [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="9eed3-124">Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="9eed3-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="9eed3-125">Non può avere qualsiasi `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="9eed3-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="9eed3-126">Una funzione iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="9eed3-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="9eed3-127">Una funzione iteratore può essere una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="9eed3-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="9eed3-128">Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="9eed3-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="9eed3-129">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="9eed3-129">Exception Handling</span></span>  
 <span data-ttu-id="9eed3-130">A `Yield` istruzione può essere contenuta in un `Try` blocco di un [Try... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9eed3-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="9eed3-131">Oggetto `Try` blocco che ha un `Yield` istruzione può avere `Catch` blocca e può avere un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="9eed3-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="9eed3-132">Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="9eed3-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="9eed3-133">Se il `For Each` corpo (all'esterno della funzione iteratore) genera un'eccezione, una `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` try nella funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="9eed3-134">Oggetto `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="9eed3-135">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="9eed3-135">Technical Implementation</span></span>  
 <span data-ttu-id="9eed3-136">Il codice seguente restituisce un `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi del `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="9eed3-137">La chiamata a `MyIteratorFunction` non esegue il corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="9eed3-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="9eed3-138">La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="9eed3-139">In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="9eed3-140">Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva.</span><span class="sxs-lookup"><span data-stu-id="9eed3-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="9eed3-141">Il `Yield` l'istruzione restituisce un'espressione che determina non solo il valore della `element` variabili per l'utilizzo dal corpo del ciclo, ma anche la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> proprietà degli elementi, ovvero un `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="9eed3-142">In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="9eed3-143">Il `For Each` ciclo viene completato quando la fine della funzione iteratore o un `Return` o `Exit Function` viene raggiunta l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9eed3-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eed3-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="9eed3-144">Example</span></span>  
 <span data-ttu-id="9eed3-145">L'esempio seguente contiene un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="9eed3-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="9eed3-146">Ogni iterazione del [per ognuno](../../../visual-basic/language-reference/statements/for-each-next-statement.md) nel corpo dell'istruzione `Main` crea una chiamata al `Power` funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="9eed3-147">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="9eed3-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="9eed3-148">Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601>, un tipo interfaccia iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="9eed3-149">Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.</span><span class="sxs-lookup"><span data-stu-id="9eed3-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="9eed3-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="9eed3-150">Example</span></span>  
 <span data-ttu-id="9eed3-151">Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="9eed3-152">La dichiarazione di proprietà contiene un `Iterator` modificatore.</span><span class="sxs-lookup"><span data-stu-id="9eed3-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="9eed3-153">Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="9eed3-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eed3-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eed3-154">See also</span></span>

- [<span data-ttu-id="9eed3-155">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="9eed3-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
