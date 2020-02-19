---
title: async - Riferimenti per C#
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 30ee13a4174a137481fbcd36ccef721958b94a12
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450856"
---
# <a name="async-c-reference"></a><span data-ttu-id="0fb97-102">async (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0fb97-102">async (C# Reference)</span></span>

<span data-ttu-id="0fb97-103">Usare il modificatore `async` per specificare che un metodo, un'[espressione lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o un [metodo anonimo](../operators/delegate-operator.md) sia asincrono.</span><span class="sxs-lookup"><span data-stu-id="0fb97-103">Use the `async` modifier to specify that a method, [lambda expression](../../programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="0fb97-104">Se si usa questo modificatore in un metodo o in un'espressione, viene indicato come *metodo asincrono*.</span><span class="sxs-lookup"><span data-stu-id="0fb97-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="0fb97-105">L'esempio seguente definisce un metodo asincrono denominato `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="0fb97-105">The following example defines an async method named `ExampleMethodAsync`:</span></span>
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

<span data-ttu-id="0fb97-106">Se non si ha esperienza di programmazione asincrona o non si sa in che modo un metodo asincrono usa l'[operatore `await`](../operators/await.md) per eseguire attività potenzialmente prolungate senza bloccare il thread del chiamante, leggere l'introduzione in [Programmazione asincrona con async e await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-106">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="0fb97-107">Il codice seguente si trova all'interno di un metodo asincrono e chiama il metodo <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="0fb97-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="0fb97-108">Un metodo asincrono viene eseguito in modo sincrono finché non raggiunge la prima espressione `await`. A quel punto, il metodo viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="0fb97-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="0fb97-109">Nel frattempo il controllo torna al chiamante del metodo, come illustrato nell'esempio della sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0fb97-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="0fb97-110">Il metodo modificato dalla parola chiave `async` viene eseguito in modo sincrono se non contiene un'espressione o un'istruzione `await`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="0fb97-111">Un avviso del compilatore segnala eventuali metodi asincroni che non contengono istruzioni `await`, perché questa situazione potrebbe indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="0fb97-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="0fb97-112">Vedere [Avviso del compilatore (livello 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-112">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="0fb97-113">La parola chiave `async` è contestuale, in quanto è una parola chiave solo quando modifica un metodo, un'espressione lambda o un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="0fb97-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="0fb97-114">In tutti gli altri contesti, viene interpretato come identificatore.</span><span class="sxs-lookup"><span data-stu-id="0fb97-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fb97-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0fb97-115">Example</span></span>  
<span data-ttu-id="0fb97-116">Nell'esempio seguente vengono illustrati la struttura e il flusso di controllo tra un gestore eventi asincrono, `StartButton_Click`, e un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="0fb97-117">Il risultato ottenuto dal metodo asincrono è il numero di caratteri di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="0fb97-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="0fb97-118">Il codice è adatto per un'applicazione Windows Presentation Foundation (WPF) o un'app di Windows Store creata in Visual Studio. Vedere i commenti del codice per l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fb97-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="0fb97-119">È possibile eseguire questo codice in Visual Studio come un'app Windows Presentation Foundation (WPF) o un'app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="0fb97-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="0fb97-120">Sono necessari un controllo Button denominato `StartButton` e un controllo Textbox denominato `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="0fb97-121">Ricordare di impostare i nomi e il gestore in modo da ottenere codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0fb97-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="0fb97-122">Per eseguire il codice come app WPF:</span><span class="sxs-lookup"><span data-stu-id="0fb97-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="0fb97-123">Incollare il codice nella classe `MainWindow` in MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="0fb97-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="0fb97-124">Aggiungere un riferimento a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="0fb97-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="0fb97-125">Aggiungere una direttiva `using` per System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="0fb97-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="0fb97-126">Per eseguire il codice come app di Windows Store:</span><span class="sxs-lookup"><span data-stu-id="0fb97-126">To run the code as a Windows Store app:</span></span>  

- <span data-ttu-id="0fb97-127">Incollare questo codice nella classe `MainPage` in MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="0fb97-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="0fb97-128">Aggiungere direttive using per System.Net.Http e System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="0fb97-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
> <span data-ttu-id="0fb97-129">Per altre informazioni sulle attività e sul codice eseguito in attesa di un'attività, vedere [Programmazione asincrona con async e await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="0fb97-130">Per un esempio di WPF completo che usa elementi simili, vedere [Procedura dettagliata: accesso al Web tramite async e await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="0fb97-131">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="0fb97-131">Return Types</span></span>  
<span data-ttu-id="0fb97-132">Un metodo asincrono può avere i tipi restituiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fb97-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="0fb97-133">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-133">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="0fb97-134">I metodi `async void` sono in genere sconsigliati per il codice diverso dai gestori eventi perché i chiamanti non possono usare `await` per questi metodi e devono implementare un meccanismo diverso per segnalare il completamento corretto o condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="0fb97-134">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="0fb97-135">A partire da C# 7.0, qualsiasi tipo con un metodo `GetAwaiter` accessibile.</span><span class="sxs-lookup"><span data-stu-id="0fb97-135">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="0fb97-136">Il tipo `System.Threading.Tasks.ValueTask<TResult>` è una di queste implementazioni</span><span class="sxs-lookup"><span data-stu-id="0fb97-136">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="0fb97-137">ed è disponibile aggiungendo il pacchetto NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-137">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="0fb97-138">Un metodo asincrono non può dichiarare parametri [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md) e nemmeno avere un [valore di riferimento restituito ](../../programming-guide/classes-and-structs/ref-returns.md), ma può chiamare metodi con tali parametri.</span><span class="sxs-lookup"><span data-stu-id="0fb97-138">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="0fb97-139">Specificare `Task<TResult>` come tipo restituito di un metodo asincrono se l'istruzione [return](./return.md) del metodo specifica un operando di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-139">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="0fb97-140">Utilizzare `Task` se non viene restituito alcun valore significativo al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="0fb97-140">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="0fb97-141">Ciò significa che una chiamata al metodo restituisce `Task`, ma al completamento di `Task`, qualsiasi espressione `await` in attesa di `Task` restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="0fb97-141">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="0fb97-142">Utilizzare il tipo restituito `void` principalmente per definire gestori eventi, che richiedono tale tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="0fb97-142">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="0fb97-143">Il chiamante di un metodo asincrono che restituisce `void` non può attendere il metodo e non può acquisire eccezioni generate dal metodo.</span><span class="sxs-lookup"><span data-stu-id="0fb97-143">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="0fb97-144">A partire da C# 7.0, viene restituito un altro tipo, in genere un tipo valore, che ha un metodo `GetAwaiter` per ridurre al minimo le allocazioni di memoria nelle sezioni di codice critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0fb97-144">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="0fb97-145">Per altre informazioni ed esempi, vedere [Tipi restituiti asincroni](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="0fb97-145">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb97-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fb97-146">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="0fb97-147">await</span><span class="sxs-lookup"><span data-stu-id="0fb97-147">await</span></span>](../operators/await.md)
- [<span data-ttu-id="0fb97-148">Procedura dettagliata: Accesso al Web tramite Async e Await</span><span class="sxs-lookup"><span data-stu-id="0fb97-148">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="0fb97-149">Programmazione asincrona con async e await</span><span class="sxs-lookup"><span data-stu-id="0fb97-149">Asynchronous Programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
