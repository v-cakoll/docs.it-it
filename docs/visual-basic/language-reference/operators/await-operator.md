---
title: Await (operatore) (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="f0277-102">Opertore Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0277-102">Await Operator (Visual Basic)</span></span>
<span data-ttu-id="f0277-103">Applicare l'operatore `Await` a un operando in un metodo o in un'espressione lambda asincroni per sospendere l'esecuzione del metodo finché l'attività di cui si è in attesa non viene completata.</span><span class="sxs-lookup"><span data-stu-id="f0277-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="f0277-104">L'attività rappresenta il lavoro attualmente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f0277-104">The task represents ongoing work.</span></span>  
  
 <span data-ttu-id="f0277-105">Il metodo in cui `Await` viene utilizzato deve avere un [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="f0277-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="f0277-106">Tale metodo, definito mediante il `Async` modificatore e in genere contiene uno o più `Await` espressioni, viene definito un *metodo asincrono*.</span><span class="sxs-lookup"><span data-stu-id="f0277-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0277-107">Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="f0277-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="f0277-108">Per un'introduzione alla programmazione asincrona, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="f0277-109">In genere, l'attività a cui si applica il `Await` operatore è il valore restituito da una chiamata a un metodo che implementa il [modello asincrono basato su attività](http://go.microsoft.com/fwlink/?LinkId=204847), vale a dire un <xref:System.Threading.Tasks.Task>o un <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="f0277-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="f0277-110">Nel codice seguente, il <xref:System.Net.Http.HttpClient>metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>restituisce `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="f0277-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="f0277-111">L'attività è una promessa di produrre la matrice di byte effettiva una volta completata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f0277-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="f0277-112">L'operatore `Await` viene applicato a `getContentsTask` per sospendere l'esecuzione in `SumPageSizesAsync` fino al completamento di `getContentsTask`.</span><span class="sxs-lookup"><span data-stu-id="f0277-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="f0277-113">Nel frattempo, il controllo viene restituito al chiamante di `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0277-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="f0277-114">Quando `getContentsTask` termina, l'espressione `Await` restituisce una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="f0277-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>  
  
<span data-ttu-id="f0277-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f0277-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="f0277-116">Per un esempio completo, vedere [procedura dettagliata: accesso al Web tramite Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-116">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="f0277-117">È possibile scaricare l'esempio da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) del sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0277-117">You can download the sample from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) on the Microsoft website.</span></span> <span data-ttu-id="f0277-118">L'esempio è nel progetto AsyncWalkthrough_HttpClient.</span><span class="sxs-lookup"><span data-stu-id="f0277-118">The example is in the AsyncWalkthrough_HttpClient project.</span></span>  
  
 <span data-ttu-id="f0277-119">Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce un elemento `Task(Of TResult)`, il tipo dell'espressione `Await` è TResult.</span><span class="sxs-lookup"><span data-stu-id="f0277-119">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="f0277-120">Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce `Task`, l'espressione `Await` non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="f0277-120">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="f0277-121">Nell'esempio che segue viene illustrata la differenza.</span><span class="sxs-lookup"><span data-stu-id="f0277-121">The following example illustrates the difference.</span></span>  
  
<span data-ttu-id="f0277-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f0277-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f0277-123">Un'espressione o un'istruzione `Await` non blocca il thread su cui è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f0277-123">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="f0277-124">Comporta invece la registrazione, tramite il compilatore, della parte restante del metodo asincrono, dopo l'espressione `Await`, come continuazione dell'attività di cui si è in attesa.</span><span class="sxs-lookup"><span data-stu-id="f0277-124">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="f0277-125">Il controllo quindi viene restituito al chiamante del metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="f0277-125">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="f0277-126">Al termine dell'attività, ne richiama la continuazione e l'esecuzione del metodo asincrono riprende da dove era stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="f0277-126">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>  
  
 <span data-ttu-id="f0277-127">Un'espressione `Await` può trovarsi solo nel corpo di un metodo che la contiene o di un'espressione lambda contrassegnata da un modificatore `Async`.</span><span class="sxs-lookup"><span data-stu-id="f0277-127">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="f0277-128">Il termine *Await* funge da parola chiave solo in tale contesto.</span><span class="sxs-lookup"><span data-stu-id="f0277-128">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="f0277-129">Altrove, viene interpretata come identificatore.</span><span class="sxs-lookup"><span data-stu-id="f0277-129">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="f0277-130">All'interno del metodo o l'espressione lambda dell'espressione asincroni, un' `Await` espressione non può verificarsi in un'espressione di query, nel `catch` o `finally` blocco di un [Try... Catch... Infine](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) istruzione, nell'espressione variabile di controllo del ciclo di un `For` o `For Each` ciclo, o nel corpo di un [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="f0277-130">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="f0277-131">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="f0277-131">Exceptions</span></span>  
 <span data-ttu-id="f0277-132">La maggior parte dei metodi asincroni restituiscono un <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="f0277-132">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f0277-133">Le proprietà dell'attività restituita contengono informazioni sullo stato e sulla cronologia, ad esempio se l'attività è stata completata, se il metodo asincrono ha generato un'eccezione o è stato annullato e il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="f0277-133">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="f0277-134">L'operatore `Await` accede a tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0277-134">The `Await` operator accesses those properties.</span></span>  
  
 <span data-ttu-id="f0277-135">Se si è in attesa di un metodo asincrono che restituisce un'attività che genera un'eccezione, tramite l'operatore `Await` viene rigenerata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f0277-135">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>  
  
 <span data-ttu-id="f0277-136">Se si attende un metodo asincrono che restituisce attività che è stato annullato, il `Await` operatore rigenera un <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException></span><span class="sxs-lookup"><span data-stu-id="f0277-136">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>  
  
 <span data-ttu-id="f0277-137">Una singola attività in uno stato di errore può rispecchiare più eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f0277-137">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="f0277-138">Ad esempio, l'attività potrebbe essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f0277-138">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="f0277-139">Quando si attende tale attività, l'operazione await rigenera solo una delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f0277-139">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="f0277-140">Tuttavia, non è possibile prevedere quale delle eccezioni verrà rigenerata.</span><span class="sxs-lookup"><span data-stu-id="f0277-140">However, you can't predict which of the exceptions is rethrown.</span></span>  
  
 <span data-ttu-id="f0277-141">Per esempi di gestione degli errori nei metodi asincroni, vedere [Try... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-141">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0277-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0277-142">Example</span></span>  
 <span data-ttu-id="f0277-143">Il seguente esempio di Windows Form illustra l'uso di `Await` in un metodo asincrono, `WaitAsynchronouslyAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0277-143">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="f0277-144">Contrastare il comportamento di tale metodo con il comportamento di `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="f0277-144">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="f0277-145">Senza un `Await` operatore `WaitSynchronously` viene eseguito in modo sincrono nonostante l'utilizzo del `Async` modificatore nella definizione e di una chiamata a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>nel relativo corpo.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f0277-145">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> in its body.</span></span>  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0277-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0277-146">See Also</span></span>  
 <span data-ttu-id="f0277-147">[Programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0277-147">[Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="f0277-148"> [Procedura dettagliata: Accesso al Web tramite Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="f0277-148"> [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="f0277-149"> [Async](../../../visual-basic/language-reference/modifiers/async.md)</span><span class="sxs-lookup"><span data-stu-id="f0277-149"> [Async](../../../visual-basic/language-reference/modifiers/async.md)</span></span>
