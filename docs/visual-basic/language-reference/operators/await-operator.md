---
title: Operatore Await
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: b5943e509bb850abc6c74e1b97ccd5fb0038f1e0
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964330"
---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="64cd6-102">Opertore Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64cd6-102">Await Operator (Visual Basic)</span></span>

<span data-ttu-id="64cd6-103">Applicare l'operatore `Await` a un operando in un metodo o in un'espressione lambda asincroni per sospendere l'esecuzione del metodo finché l'attività di cui si è in attesa non viene completata.</span><span class="sxs-lookup"><span data-stu-id="64cd6-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="64cd6-104">L'attività rappresenta il lavoro attualmente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64cd6-104">The task represents ongoing work.</span></span>

<span data-ttu-id="64cd6-105">Il metodo in cui viene usato `Await` deve avere un modificatore [Async](../../../visual-basic/language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="64cd6-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="64cd6-106">Tale metodo, definito usando il modificatore `Async` e contenente di solito una o più espressioni `Await`, viene denominato *metodo asincrono*.</span><span class="sxs-lookup"><span data-stu-id="64cd6-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>

> [!NOTE]
> <span data-ttu-id="64cd6-107">Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="64cd6-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="64cd6-108">Per un'introduzione alla programmazione asincrona, vedere [programmazione asincrona con Async e await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="64cd6-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="64cd6-109">In genere, l'attività a cui si applica l'operatore `Await` è il valore restituito da una chiamata a un metodo che implementa il [modello asincrono basato su attività](https://www.microsoft.com/download/details.aspx?id=19957), ovvero una <xref:System.Threading.Tasks.Task> o un <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="64cd6-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](https://www.microsoft.com/download/details.aspx?id=19957), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="64cd6-110">Nel seguente codice, l'elemento <xref:System.Net.Http.HttpClient> del metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> restituisce `getContentsTask`, un elemento `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="64cd6-111">L'attività è una promessa di produrre la matrice di byte effettiva una volta completata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="64cd6-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="64cd6-112">L'operatore `Await` viene applicato a `getContentsTask` per sospendere l'esecuzione in `SumPageSizesAsync` fino al completamento di `getContentsTask`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="64cd6-113">Nel frattempo, il controllo viene restituito al chiamante di `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="64cd6-114">Quando `getContentsTask` termina, l'espressione `Await` restituisce una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="64cd6-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>

```vb
Private Async Function SumPageSizesAsync() As Task

    ' To use the HttpClient type in desktop apps, you must include a using directive and add a
    ' reference for the System.Net.Http namespace.
    Dim client As HttpClient = New HttpClient()
    ' . . .
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    Dim urlContents As Byte() = Await getContentsTask

    ' Equivalently, now that you see how it works, you can write the same thing in a single line.
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ' . . .
End Function
```

> [!IMPORTANT]
> <span data-ttu-id="64cd6-115">Per l'esempio completo, vedere [Procedura dettagliata: accesso al Web con async e await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="64cd6-115">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="64cd6-116">È possibile scaricare l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per sviluppatori) del sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64cd6-116">You can download the sample from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) on the Microsoft website.</span></span> <span data-ttu-id="64cd6-117">L'esempio è nel progetto AsyncWalkthrough_HttpClient.</span><span class="sxs-lookup"><span data-stu-id="64cd6-117">The example is in the AsyncWalkthrough_HttpClient project.</span></span>

<span data-ttu-id="64cd6-118">Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce un elemento `Task(Of TResult)`, il tipo dell'espressione `Await` è TResult.</span><span class="sxs-lookup"><span data-stu-id="64cd6-118">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="64cd6-119">Se `Await` viene applicato al risultato di una chiamata a un metodo che restituisce `Task`, l'espressione `Await` non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="64cd6-119">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="64cd6-120">Nell'esempio che segue viene illustrata la differenza.</span><span class="sxs-lookup"><span data-stu-id="64cd6-120">The following example illustrates the difference.</span></span>

```vb
' Await used with a method that returns a Task(Of TResult).
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()

' Await used with a method that returns a Task.
Await AsyncMethodThatReturnsTask()
```

<span data-ttu-id="64cd6-121">Un'espressione o un'istruzione `Await` non blocca il thread su cui è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64cd6-121">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="64cd6-122">Comporta invece la registrazione, tramite il compilatore, della parte restante del metodo asincrono, dopo l'espressione `Await`, come continuazione dell'attività di cui si è in attesa.</span><span class="sxs-lookup"><span data-stu-id="64cd6-122">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="64cd6-123">Il controllo quindi viene restituito al chiamante del metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="64cd6-123">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="64cd6-124">Al termine dell'attività, ne richiama la continuazione e l'esecuzione del metodo asincrono riprende da dove era stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="64cd6-124">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>

<span data-ttu-id="64cd6-125">Un'espressione `Await` può trovarsi solo nel corpo di un metodo che la contiene o di un'espressione lambda contrassegnata da un modificatore `Async`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-125">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="64cd6-126">Il termine *await* funge da parola chiave solo in tale contesto.</span><span class="sxs-lookup"><span data-stu-id="64cd6-126">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="64cd6-127">Altrove, viene interpretata come identificatore.</span><span class="sxs-lookup"><span data-stu-id="64cd6-127">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="64cd6-128">All'interno del metodo `Async` o dell'espressione lambda, un'espressione `Await` non può essere presente in un'espressione di query, nel blocco `Catch` o `Finally` di un [try... Rileva... Infine](../statements/try-catch-finally-statement.md), nell'espressione variabile di controllo del ciclo di un `For` o `For Each` ciclo oppure nel corpo di un'istruzione [SyncLock](../statements/synclock-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="64cd6-128">Within the `Async` method or lambda expression, an `Await` expression cannot occur in a query expression, in the `Catch` or `Finally` block of a [Try…Catch…Finally statement](../statements/try-catch-finally-statement.md), in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../statements/synclock-statement.md) statement.</span></span>

## <a name="exceptions"></a><span data-ttu-id="64cd6-129">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="64cd6-129">Exceptions</span></span>

<span data-ttu-id="64cd6-130">La maggior parte dei metodi asincroni restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="64cd6-130">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="64cd6-131">Le proprietà dell'attività restituita contengono informazioni sullo stato e sulla cronologia, ad esempio se l'attività è stata completata, se il metodo asincrono ha generato un'eccezione o è stato annullato e il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="64cd6-131">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="64cd6-132">L'operatore `Await` accede a tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="64cd6-132">The `Await` operator accesses those properties.</span></span>

<span data-ttu-id="64cd6-133">Se si è in attesa di un metodo asincrono che restituisce un'attività che genera un'eccezione, tramite l'operatore `Await` viene rigenerata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="64cd6-133">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>

<span data-ttu-id="64cd6-134">Se si è in attesa di un metodo asincrono che restituisce un'attività che è stato annullato, tramite l'operatore `Await` viene rigenerata un'eccezione <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="64cd6-134">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="64cd6-135">Una singola attività in uno stato di errore può rispecchiare più eccezioni.</span><span class="sxs-lookup"><span data-stu-id="64cd6-135">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="64cd6-136">Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64cd6-136">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64cd6-137">Quando si attende tale attività, l'operazione await rigenera solo una delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="64cd6-137">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="64cd6-138">Tuttavia, non è possibile prevedere quale delle eccezioni verrà rigenerata.</span><span class="sxs-lookup"><span data-stu-id="64cd6-138">However, you can't predict which of the exceptions is rethrown.</span></span>

<span data-ttu-id="64cd6-139">Per esempi di gestione degli errori nei metodi asincroni, vedere [try... Rileva... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64cd6-139">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="64cd6-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="64cd6-140">Example</span></span>

<span data-ttu-id="64cd6-141">Il seguente esempio di Windows Form illustra l'uso di `Await` in un metodo asincrono, `WaitAsynchronouslyAsync`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-141">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="64cd6-142">Contrastare il comportamento di tale metodo con il comportamento di `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="64cd6-142">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="64cd6-143">Senza un operatore `Await`, `WaitSynchronously` viene eseguito in modo sincrono nonostante l'uso del modificatore `Async` nella definizione e di una chiamata a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> nel corpo.</span><span class="sxs-lookup"><span data-stu-id="64cd6-143">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> in its body.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="64cd6-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64cd6-144">See also</span></span>

- [<span data-ttu-id="64cd6-145">Programmazione asincrona con Async e Await</span><span class="sxs-lookup"><span data-stu-id="64cd6-145">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="64cd6-146">Procedura dettagliata: Accesso al Web tramite Async e Await</span><span class="sxs-lookup"><span data-stu-id="64cd6-146">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="64cd6-147">Async</span><span class="sxs-lookup"><span data-stu-id="64cd6-147">Async</span></span>](../../../visual-basic/language-reference/modifiers/async.md)
