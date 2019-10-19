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
ms.openlocfilehash: 57b36bb32e1a575a645f7a15045bf0898dd10dfd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582209"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="1fdf3-102">Istruzione Yield (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fdf3-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="1fdf3-103">Invia l'elemento successivo di una raccolta a un'istruzione `For Each...Next`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fdf3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fdf3-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fdf3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1fdf3-105">Parameters</span></span>  
  
|<span data-ttu-id="1fdf3-106">Termine</span><span class="sxs-lookup"><span data-stu-id="1fdf3-106">Term</span></span>|<span data-ttu-id="1fdf3-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="1fdf3-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="1fdf3-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-108">Required.</span></span> <span data-ttu-id="1fdf3-109">Espressione convertibile in modo implicito nel tipo della funzione iteratore o `Get` funzione di accesso che contiene l'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fdf3-110">Note</span><span class="sxs-lookup"><span data-stu-id="1fdf3-110">Remarks</span></span>  
 <span data-ttu-id="1fdf3-111">L'istruzione `Yield` restituisce un elemento di una raccolta alla volta.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="1fdf3-112">L'istruzione `Yield` è inclusa in una funzione iteratore o in una funzione di accesso `Get`, che esegue iterazioni personalizzate su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="1fdf3-113">Si utilizza una funzione iteratore utilizzando un [per ogni... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o query LINQ.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="1fdf3-114">Ogni iterazione del ciclo `For Each` chiama la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="1fdf3-115">Quando viene raggiunta un'istruzione `Yield` nella funzione iteratore, viene restituito `expression` e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="1fdf3-116">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="1fdf3-117">Deve esistere una conversione implicita dal tipo di `expression` nell'istruzione `Yield` al tipo restituito dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="1fdf3-118">Per terminare l'iterazione, è possibile usare un'istruzione `Exit Function` o `Return`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="1fdf3-119">"Yield" non è una parola riservata e ha un significato speciale solo quando viene usato in una funzione `Iterator` o in una funzione di accesso `Get`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="1fdf3-120">Per ulteriori informazioni sulle funzioni iteratori e sulle funzioni di accesso `Get`, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="1fdf3-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="1fdf3-121">Funzioni iteratori e funzioni di accesso get</span><span class="sxs-lookup"><span data-stu-id="1fdf3-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="1fdf3-122">La dichiarazione di una funzione iteratore o di una funzione di accesso `Get` deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fdf3-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="1fdf3-123">Deve includere un modificatore [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) .</span><span class="sxs-lookup"><span data-stu-id="1fdf3-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="1fdf3-124">Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="1fdf3-125">Non può avere parametri `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="1fdf3-126">Una funzione iteratore non può verificarsi in un evento, in un costruttore di istanza, in un costruttore statico o in un distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="1fdf3-127">Una funzione iteratore può essere una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="1fdf3-128">Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="1fdf3-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="1fdf3-129">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="1fdf3-129">Exception Handling</span></span>  
 <span data-ttu-id="1fdf3-130">Un'istruzione `Yield` può trovarsi all'interno di un blocco `Try` di un oggetto [try... Rileva... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1fdf3-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="1fdf3-131">Un blocco di `Try` con un'istruzione `Yield` può avere `Catch` blocchi e può avere un blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="1fdf3-132">Un'istruzione `Yield` non può trovarsi all'interno di un blocco di `Catch` o di un blocco di `Finally`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="1fdf3-133">Se il corpo del `For Each` (all'esterno della funzione iteratore) genera un'eccezione, un blocco di `Catch` nella funzione iteratore non viene eseguito, ma viene eseguito un blocco `Finally` nella funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="1fdf3-134">Un blocco `Catch` all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="1fdf3-135">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="1fdf3-135">Technical Implementation</span></span>  
 <span data-ttu-id="1fdf3-136">Il codice seguente restituisce un `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi della `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="1fdf3-137">La chiamata a `MyIteratorFunction` non esegue il corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="1fdf3-138">La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="1fdf3-139">In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="1fdf3-140">Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="1fdf3-141">L'istruzione `Yield` restituisce un'espressione che determina non solo il valore della variabile `element` per l'utilizzo da parte del corpo del ciclo, ma anche la proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A> degli elementi, che è un `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="1fdf3-142">In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="1fdf3-143">Il ciclo `For Each` viene completato quando viene raggiunta la fine della funzione iteratore o di un'istruzione `Return` o `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fdf3-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fdf3-144">Example</span></span>  
 <span data-ttu-id="1fdf3-145">Nell'esempio seguente è presente un'istruzione `Yield` che si trova all'interno di un oggetto [per... Ciclo successivo](../../../visual-basic/language-reference/statements/for-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="1fdf3-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="1fdf3-146">Ogni iterazione del corpo dell'istruzione [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in `Main` crea una chiamata al `Power` funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="1fdf3-147">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="1fdf3-148">Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601>, un tipo di interfaccia iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="1fdf3-149">Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="1fdf3-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fdf3-150">Example</span></span>  
 <span data-ttu-id="1fdf3-151">Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="1fdf3-152">La dichiarazione di proprietà include un modificatore `Iterator`.</span><span class="sxs-lookup"><span data-stu-id="1fdf3-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="1fdf3-153">Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="1fdf3-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fdf3-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fdf3-154">See also</span></span>

- [<span data-ttu-id="1fdf3-155">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="1fdf3-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
