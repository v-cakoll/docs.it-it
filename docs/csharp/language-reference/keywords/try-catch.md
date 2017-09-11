---
title: try-catch (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b7ec6c96ac21ba2115d1e7eead5700b6dbfcc952
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-c-reference"></a><span data-ttu-id="cf4c7-102">try-catch (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cf4c7-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="cf4c7-103">L'istruzione try-catch è costituita da un blocco `try` seguito da una o più clausole `catch`, che specificano i gestori per eccezioni diverse.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf4c7-104">Note</span><span class="sxs-lookup"><span data-stu-id="cf4c7-104">Remarks</span></span>  
 <span data-ttu-id="cf4c7-105">Quando viene generata un'eccezione, Common Language Runtime(CLR) cerca l'istruzione `catch` che gestisce questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="cf4c7-106">Se il metodo attualmente in esecuzione non contiene tale blocco `catch`, CLR analizza il metodo che ha chiamato il metodo corrente e così via fino allo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="cf4c7-107">Se non viene trovato alcun blocco `catch`, CLR visualizza un messaggio di eccezione non gestita per l'utente e interrompe l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="cf4c7-108">Il blocco `try` contiene il codice protetto che potrebbe generare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="cf4c7-109">Il blocco viene eseguito fino a quando non viene generata un'eccezione o viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="cf4c7-110">Ad esempio, il seguente tentativo di eseguire il cast di un oggetto `null` genera l'eccezione <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="cf4c7-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="cf4c7-111">Anche se la clausola `catch` può essere usata senza argomenti per intercettare qualsiasi tipo di eccezione, questo utilizzo non è consigliato.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="cf4c7-112">In generale, è consigliabile intercettare solo le eccezioni di cui si sa come eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="cf4c7-113">È quindi opportuno specificare sempre argomento di oggetto derivato da <xref:System.Exception?displayProperty=fullName>, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf4c7-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=fullName> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="cf4c7-114">È possibile usare più clausole `catch` specifiche nella stessa istruzione try-catch.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="cf4c7-115">In questo caso, l'ordine delle clausole `catch` è importante perché le clausole `catch` vengono esaminate nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="cf4c7-116">Intercettare le eccezioni più specifiche prima di quelle meno specifiche.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="cf4c7-117">Il compilatore provoca un errore se si ordinano i blocchi catch in modo che un blocco successivo non possa mai essere raggiunto.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="cf4c7-118">Usando gli argomenti `catch`, è possibile filtrare le eccezioni che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="cf4c7-119">È inoltre possibile usare un'espressione del predicato che esamini ulteriormente l'eccezione per decidere se gestirla.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="cf4c7-120">Se l'espressione del predicato restituisce false, la ricerca di un gestore prosegue.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="cf4c7-121">I filtri eccezioni sono preferibili per l'intercettazione e la rigenerazione (come illustrato di seguito) perché lasciano intatto lo stack.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="cf4c7-122">Se un gestore successivo esegue il dump dello stack, è possibile visualizzare l'origine dell'eccezione, anziché solo l'ultima posizione in cui è stata rigenerata.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="cf4c7-123">Un uso comune delle espressioni di filtro eccezioni è la registrazione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="cf4c7-124">È possibile creare una funzione predicato che restituisca sempre false da visualizzare anche in un log. È possibile registrare le eccezioni mentre si verificano senza doverle gestire e rigenerare.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="cf4c7-125">Un'istruzione [throw](../../../csharp/language-reference/keywords/throw.md) può essere usata in un blocco `catch` per rigenerare l'eccezione intercettata dall'istruzione `catch`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="cf4c7-126">Il seguente esempio estrae le informazioni di origine da un'eccezione <xref:System.IO.IOException> e quindi genera l'eccezione per il metodo padre.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
```csharp  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    if (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 <span data-ttu-id="cf4c7-127">È possibile intercettare un'eccezione e generarne un'altra.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="cf4c7-128">In questo caso, specificare l'eccezione intercettata come eccezione interna, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="cf4c7-129">È anche possibile generare nuovamente un'eccezione quando una determinata condizione è true, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 <span data-ttu-id="cf4c7-130">Da un blocco `try` inizializzare solo le variabili dichiarate al suo interno.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="cf4c7-131">In caso contrario, è possibile che si verifichi un'eccezione prima del completamento dell'esecuzione del blocco.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="cf4c7-132">Nel seguente esempio di codice, la variabile `n` viene inizializzata nel blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="cf4c7-133">Un tentativo di usare questa variabile al di fuori del blocco `try` nell'istruzione `Write(n)` genererà un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
```csharp  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 <span data-ttu-id="cf4c7-134">Per altre informazioni su catch, vedere [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="cf4c7-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="cf4c7-135">Eccezioni nei metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="cf4c7-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="cf4c7-136">Un metodo asincrono viene contrassegnato da un modificatore [async](../../../csharp/language-reference/keywords/async.md) e in genere contiene una o più espressioni o istruzioni await.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="cf4c7-137">Un'espressione await applica l'operatore [await](../../../csharp/language-reference/keywords/await.md) a un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="cf4c7-138">Quando il controllo raggiunge un oggetto `await` nel metodo asincrono, l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="cf4c7-139">Una volta completata l'attività, l'esecuzione del metodo può riprendere.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="cf4c7-140">Per altre informazioni, vedere [Programmazione asincrona con Async e Await](../../../csharp/programming-guide/concepts/async/index.md) e [Flusso di controllo in programmi asincroni](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="cf4c7-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="cf4c7-141">L'attività completata a cui viene applicato `await` può essere in uno stato di errore a causa di un'eccezione non gestita nel metodo che restituisce l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="cf4c7-142">L'attesa dell'attività genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="cf4c7-143">Un'attività può inoltre terminare con uno stato di annullamento se viene annullato il processo asincrono che la restituisce.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="cf4c7-144">L'attesa di un'attività annullata genera un'eccezione `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="cf4c7-145">Per altre informazioni su come annullare un processo asincrono, vedere [Ottimizzazione dell'applicazione Async](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span><span class="sxs-lookup"><span data-stu-id="cf4c7-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span></span>  
  
 <span data-ttu-id="cf4c7-146">Per intercettare l'eccezione, attendere l'attività in un blocco `try` e intercettare l'eccezione nel blocco `catch` associato.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="cf4c7-147">Per un esempio, vedere la sezione "Esempio".</span><span class="sxs-lookup"><span data-stu-id="cf4c7-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="cf4c7-148">Un'attività può essere in uno stato di errore perché si sono verificate più eccezioni nel metodo asincrono atteso.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="cf4c7-149">Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="cf4c7-150">Quando si attende tale attività, solo una delle eccezioni viene intercettata, ma non è possibile prevedere quale.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="cf4c7-151">Per un esempio, vedere la sezione "Esempio".</span><span class="sxs-lookup"><span data-stu-id="cf4c7-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4c7-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf4c7-152">Example</span></span>  
 <span data-ttu-id="cf4c7-153">Nel seguente esempio, il blocco `try` contiene una chiamata al metodo `ProcessString` che potrebbe causare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="cf4c7-154">La clausola `catch` contiene il gestore di eccezioni che visualizza solo un messaggio sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="cf4c7-155">Quando l'istruzione `throw` viene chiamata da `MyMethod`, il sistema cerca l'istruzione `catch` e visualizza il messaggio `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 <span data-ttu-id="cf4c7-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf4c7-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4c7-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf4c7-157">Example</span></span>  
 <span data-ttu-id="cf4c7-158">Nell'esempio seguente, vengono usati due blocchi catch e viene intercettata l'eccezione più specifica, che è la prima.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-158">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="cf4c7-159">Per intercettare l'eccezione meno specifica, è possibile sostituire l'istruzione throw in `ProcessString` con l'istruzione seguente: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-159">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="cf4c7-160">Se nell'esempio si inserisce per primo il blocco catch meno specifico, viene visualizzato il messaggio di errore seguente: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-160">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 <span data-ttu-id="cf4c7-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf4c7-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4c7-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf4c7-162">Example</span></span>  
 <span data-ttu-id="cf4c7-163">L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="cf4c7-164">Per intercettare un'eccezione generata da un'attività asincrona, inserire l'espressione `await` in un blocco `try` e intercettare l'eccezione in un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="cf4c7-165">Rimuovere il commento dalla riga `throw new Exception` nell'esempio per illustrare la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="cf4c7-166">La proprietà `IsFaulted` dell'attività viene impostata su `True`, la proprietà `Exception.InnerException` dell'attività viene impostata sull'eccezione e l'eccezione viene intercettata nel blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="cf4c7-167">Rimuovere il commento dalla riga `throw new OperationCancelledException` per illustrare cosa accade quando si annulla un processo asincrono.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-167">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="cf4c7-168">La proprietà `IsCanceled` dell'attività viene impostata su `true` e l'eccezione viene intercettata nel blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="cf4c7-169">In alcune condizioni che non si applicano a questo esempio, la proprietà `IsFaulted` dell'attività viene impostata su `true` e `IsCanceled` viene impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 <span data-ttu-id="cf4c7-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf4c7-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4c7-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf4c7-171">Example</span></span>  
 <span data-ttu-id="cf4c7-172">Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-172">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="cf4c7-173">Il blocco `try` attende l'attività restituita da una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-173">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="cf4c7-174">L'attività viene completata quando vengono completate le tre attività a cui si applica WhenAll.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-174">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="cf4c7-175">Ognuna delle tre attività genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-175">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="cf4c7-176">Il blocco `catch` scorre le eccezioni presenti nella proprietà `Exception.InnerExceptions` dell'attività restituita da <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="cf4c7-176">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="cf4c7-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf4c7-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="cf4c7-178">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cf4c7-178">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf4c7-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf4c7-179">See Also</span></span>  
 <span data-ttu-id="cf4c7-180">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-180">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cf4c7-181">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-181">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cf4c7-182">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-182">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="cf4c7-183">[Istruzioni try, throw e catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-183">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="cf4c7-184">[Istruzioni di gestione delle eccezioni](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-184">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="cf4c7-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="cf4c7-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="cf4c7-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="cf4c7-187">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="cf4c7-187">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

