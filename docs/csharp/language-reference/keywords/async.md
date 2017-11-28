---
title: async (Riferimenti per C#)
ms.date: 05/22/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: "52"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4a89736822342a9d9a24db6d43435f9795b81b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="async-c-reference"></a><span data-ttu-id="7da6d-102">async (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7da6d-102">async (C# Reference)</span></span>
<span data-ttu-id="7da6d-103">Usare il modificatore `async` per specificare che un metodo, un'[espressione lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) o un [metodo anonimo](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) sia asincrono.</span><span class="sxs-lookup"><span data-stu-id="7da6d-103">Use the `async` modifier to specify that a method, [lambda expression](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) is asynchronous.</span></span> <span data-ttu-id="7da6d-104">Se si usa questo modificatore in un metodo o in un'espressione, viene indicato come *metodo asincrono*.</span><span class="sxs-lookup"><span data-stu-id="7da6d-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="7da6d-105">L'esempio seguente definisce un metodo asincrono denominato `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="7da6d-105">The following example defines an async method named `ExampleMethodAsync`:</span></span> 
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  
 
<span data-ttu-id="7da6d-106">Se non si ha esperienza di programmazione asincrona o non si sa in che modo un metodo asincrono usa la parola chiave `await` per eseguire attività potenzialmente prolungate senza bloccare il thread del chiamante, leggere l'introduzione in [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="7da6d-106">If you're new to asynchronous programming or do not understand how an async method uses the `await` keyword to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="7da6d-107">Il codice seguente si trova all'interno di un metodo asincrono e chiama il metodo <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="7da6d-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span> 
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="7da6d-108">Un metodo asincrono viene eseguito in modo sincrono finché non raggiunge la prima espressione `await`. A quel punto, il metodo viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="7da6d-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="7da6d-109">Nel frattempo il controllo torna al chiamante del metodo, come illustrato nell'esempio della sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="7da6d-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="7da6d-110">Il metodo modificato dalla parola chiave `async` viene eseguito in modo sincrono se non contiene un'espressione o un'istruzione `await`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="7da6d-111">Un avviso del compilatore segnala eventuali metodi asincroni che non contengono istruzioni `await`, perché questa situazione potrebbe indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="7da6d-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="7da6d-112">Vedere [Avviso del compilatore (livello 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="7da6d-112">See [Compiler Warning (level 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="7da6d-113">La parola chiave `async` è contestuale, in quanto è una parola chiave solo quando modifica un metodo, un'espressione lambda o un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="7da6d-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="7da6d-114">In tutti gli altri contesti, viene interpretato come identificatore.</span><span class="sxs-lookup"><span data-stu-id="7da6d-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da6d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7da6d-115">Example</span></span>  
<span data-ttu-id="7da6d-116">Nell'esempio seguente vengono illustrati la struttura e il flusso di controllo tra un gestore eventi asincrono, `StartButton_Click`, e un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="7da6d-117">Il risultato ottenuto dal metodo asincrono è il numero di caratteri di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="7da6d-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="7da6d-118">Il codice è adatto per un'applicazione Windows Presentation Foundation (WPF) o un'app di Windows Store creata in Visual Studio. Vedere i commenti del codice per l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7da6d-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="7da6d-119">È possibile eseguire questo codice in Visual Studio come un'app Windows Presentation Foundation (WPF) o un'app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="7da6d-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="7da6d-120">Sono necessari un controllo Button denominato `StartButton` e un controllo Textbox denominato `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="7da6d-121">Ricordare di impostare i nomi e il gestore in modo da ottenere codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7da6d-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="7da6d-122">Per eseguire il codice come app WPF:</span><span class="sxs-lookup"><span data-stu-id="7da6d-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="7da6d-123">Incollare il codice nella classe `MainWindow` in MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="7da6d-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="7da6d-124">Aggiungere un riferimento a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="7da6d-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="7da6d-125">Aggiungere una direttiva `using` per System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="7da6d-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="7da6d-126">Per eseguire il codice come app di Windows Store:</span><span class="sxs-lookup"><span data-stu-id="7da6d-126">To run the code as a Windows Store app:</span></span>  
- <span data-ttu-id="7da6d-127">Incollare questo codice nella classe `MainPage` in MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="7da6d-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="7da6d-128">Aggiungere direttive using per System.Net.Http e System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="7da6d-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
>  <span data-ttu-id="7da6d-129">Per altre informazioni sulle attività e sul codice eseguito in attesa di un'attività, vedere [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="7da6d-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="7da6d-130">Per un esempio di WPF completo che usa elementi simili, vedere [Procedura dettagliata: accesso al Web tramite async e await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="7da6d-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="7da6d-131">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="7da6d-131">Return Types</span></span>  
<span data-ttu-id="7da6d-132">Un metodo asincrono può avere i tipi restituiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7da6d-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="7da6d-133">[void](../../../csharp/language-reference/keywords/void.md), che deve essere usato solo per i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="7da6d-133">[void](../../../csharp/language-reference/keywords/void.md), which should only be used for event handlers.</span></span>
- <span data-ttu-id="7da6d-134">A partire da C# 7, qualsiasi tipo con un metodo `GetAwaiter` accessibile.</span><span class="sxs-lookup"><span data-stu-id="7da6d-134">Starting with C# 7, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="7da6d-135">Il tipo `System.Threading.Tasks.ValueTask<TResult>` è una di queste implementazioni</span><span class="sxs-lookup"><span data-stu-id="7da6d-135">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="7da6d-136">ed è disponibile aggiungendo il pacchetto NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-136">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="7da6d-137">Un metodo asincrono non può dichiarare parametri [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md) e nemmeno avere un valore di riferimento restituito <!-- [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) -->, ma può chiamare metodi con tali parametri.</span><span class="sxs-lookup"><span data-stu-id="7da6d-137">The async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters, nor can it have a <!-- [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) -->reference return value, but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="7da6d-138">Specificare `Task<TResult>` come tipo restituito di un metodo asincrono se l'istruzione [return](../../../csharp/language-reference/keywords/return.md) del metodo specifica un operando di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-138">You specify `Task<TResult>` as the return type of an async method if the [return](../../../csharp/language-reference/keywords/return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="7da6d-139">Utilizzare `Task` se non viene restituito alcun valore significativo al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="7da6d-139">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="7da6d-140">Ciò significa che una chiamata al metodo restituisce `Task`, ma al completamento di `Task`, qualsiasi espressione `await` in attesa di `Task` restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="7da6d-140">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="7da6d-141">Utilizzare il tipo restituito `void` principalmente per definire gestori eventi, che richiedono tale tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="7da6d-141">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="7da6d-142">Il chiamante di un metodo asincrono che restituisce `void` non può attendere il metodo e non può acquisire eccezioni generate dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7da6d-142">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="7da6d-143">A partire da C# 7, si restituisce a un altro tipo, in genere un tipo valore, che ha un metodo `GetAwaiter` per ridurre al minimo le allocazioni di memoria nelle sezioni del codice critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7da6d-143">Starting with C# 7, you return another type, typically a value type, that has a `GetAwaiter` method to miminize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="7da6d-144">Per altre informazioni ed esempi, vedere [Tipi restituiti asincroni](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7da6d-144">For more information and examples, see [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da6d-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7da6d-145">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [<span data-ttu-id="7da6d-146">await</span><span class="sxs-lookup"><span data-stu-id="7da6d-146">await</span></span>](../../../csharp/language-reference/keywords/await.md)  
 [<span data-ttu-id="7da6d-147">Procedura dettagliata: Accesso al Web tramite Async e Await</span><span class="sxs-lookup"><span data-stu-id="7da6d-147">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="7da6d-148">Programmazione asincrona con async e await</span><span class="sxs-lookup"><span data-stu-id="7da6d-148">Asynchronous Programming with async and await</span></span>](../../../csharp/programming-guide/concepts/async/index.md)
