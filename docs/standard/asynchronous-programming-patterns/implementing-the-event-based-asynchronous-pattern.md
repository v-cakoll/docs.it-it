---
title: Implementazione del modello asincrono basato su eventi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: 9865fa169e0776765f9a97ec0a7b4555bf253886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67663711"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="d8ca4-102">Implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-102">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="d8ca4-103">In caso di scrittura di una classe con alcune operazioni che possono causare ritardi notevoli, è consigliabile assegnare la funzionalità asincrona implementando [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="d8ca4-104">Il modello asincrono basato su eventi offre un modo standardizzato per aggiungere funzionalità asincrone a una classe.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-104">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="d8ca4-105">Se implementata con classi helper come <xref:System.ComponentModel.AsyncOperationManager>, la classe funzionerà con qualsiasi modello di applicazione, tra cui ASP.NET, applicazioni console e Windows Forms Application.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-105">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="d8ca4-106">Per un esempio che implementa il modello asincrono basato su eventi, vedere [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-106">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="d8ca4-107">Per operazioni asincrone semplici, può risultare idoneo il componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-107">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="d8ca4-108">Per altre informazioni su <xref:System.ComponentModel.BackgroundWorker>, vedere [Procedura: eseguire un'operazione in background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-108">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="d8ca4-109">L'elenco seguente descrive le funzionalità del modello asincrono basato su eventi affrontate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-109">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="d8ca4-110">Opportunità per implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-110">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="d8ca4-111">Denominazione di metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="d8ca4-111">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="d8ca4-112">Supporto facoltativo dell'annullamento</span><span class="sxs-lookup"><span data-stu-id="d8ca4-112">Optionally Support Cancellation</span></span>

- <span data-ttu-id="d8ca4-113">Supporto facoltativo della proprietà IsBusy</span><span class="sxs-lookup"><span data-stu-id="d8ca4-113">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="d8ca4-114">Supporto facoltativo per la generazione di report sullo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="d8ca4-114">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="d8ca4-115">Supporto facoltativo per la restituzione di risultati incrementali</span><span class="sxs-lookup"><span data-stu-id="d8ca4-115">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="d8ca4-116">Gestione dei parametri Out e Ref nei metodi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-116">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="d8ca4-117">Opportunità per implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-117">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="d8ca4-118">Valutare l'implementazione del modello asincrono basato su eventi quando:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-118">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="d8ca4-119">I client della classe non richiedono che siano disponibili oggetti <xref:System.Threading.WaitHandle> e <xref:System.IAsyncResult> per le operazioni asincrone, quindi il polling e il metodo <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> devono essere compilati dal client.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-119">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="d8ca4-120">Si desidera che le operazioni asincrone vengano gestite dal client con il modello noto di evento/delegato.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-120">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="d8ca4-121">Qualsiasi operazione è un candidato per un'implementazione asincrona, ma è opportuno considerare quelle con lunghe latenze previste.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-121">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="d8ca4-122">Sono particolarmente indicate le operazioni in cui i client chiamano un metodo e ricevono una notifica al completamento, senza richiedere ulteriori interventi.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-122">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="d8ca4-123">Rientrano in questa condizione anche le operazioni con esecuzione continua,che inviano notifiche periodiche ai client sullo stato di avanzamento, sui risultati incrementali o sulle modifiche di stato.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-123">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="d8ca4-124">Per altre informazioni sui casi in cui supportare il modello asincrono basato su eventi, vedere [Quando implementare il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-124">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="d8ca4-125">Denominazione di metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="d8ca4-125">Naming Asynchronous Methods</span></span>

<span data-ttu-id="d8ca4-126">Per ogni metodo *MethodName* sincrono per il quale si desidera specificare una controparte asincrona:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-126">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="d8ca4-127">Definire un metodo MethodName Async che:Define a _MethodName_**Async** method that:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-127">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="d8ca4-128">Restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-128">Returns `void`.</span></span>

- <span data-ttu-id="d8ca4-129">Accetta gli stessi parametri del metodo *MethodName*.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-129">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="d8ca4-130">Accetta più chiamate.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-130">Accepts multiple invocations.</span></span>

<span data-ttu-id="d8ca4-131">Facoltativamente, definire un overload _MethodName_**Async,** identico a _NomeMetodo_**Async**, ma con un parametro con valori di oggetto aggiuntivo denominato `userState`.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-131">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="d8ca4-132">Seguire questa procedura se si intende gestire più chiamate simultanee del metodo, nel qual caso il valore `userState` verrà recapitato nuovamente a tutti i gestori eventi per distinguere le chiamate del metodo.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-132">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="d8ca4-133">È anche possibile scegliere questa opzione come posizione in cui archiviare lo stato utente per un successivo recupero.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-133">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="d8ca4-134">Per ogni firma del metodo MethodName Async separata:For each separate _MethodName_**Async** method signature:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-134">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="d8ca4-135">Definire l'evento seguente nella stessa classe del metodo:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-135">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="d8ca4-136">Definire il delegato seguente e <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-136">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="d8ca4-137">che verranno probabilmente definiti all'esterno della classe, ma nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-137">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

    ```vb
    Public Delegate Sub MethodNameCompletedEventHandler( _
        ByVal sender As Object, _
        ByVal e As MethodNameCompletedEventArgs)

    Public Class MethodNameCompletedEventArgs
        Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As MyReturnType
    End Property
    ```

    ```csharp
    public delegate void MethodNameCompletedEventHandler(object sender,
        MethodNameCompletedEventArgs e);

    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
    {
        public MyReturnType Result { get; }
    }
    ```

    - <span data-ttu-id="d8ca4-138">Assicurarsi che la classe _MethodName_**CompletedEventArgs** esponga i relativi membri come proprietà di sola lettura e non come campi, poiché i campi impediscono l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-138">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="d8ca4-139">Non definire alcuna classe derivata da <xref:System.ComponentModel.AsyncCompletedEventArgs> per i metodi che non producono risultati.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-139">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="d8ca4-140">Usare semplicemente un'istanza di <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-140">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d8ca4-141">È perfettamente accettabile, quando possibile e appropriato, riutilizzare il delegato e i tipi <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-141">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="d8ca4-142">In questo caso, la denominazione non sarà coerente con il nome del metodo, perché un delegato e un oggetto <xref:System.ComponentModel.AsyncCompletedEventArgs> specifici non saranno associati a un singolo metodo.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-142">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="d8ca4-143">Supporto facoltativo dell'annullamento</span><span class="sxs-lookup"><span data-stu-id="d8ca4-143">Optionally Support Cancellation</span></span>

<span data-ttu-id="d8ca4-144">Se la classe supporta l'annullamento delle operazioni asincrone, l'annullamento dovrebbe essere esposto al client come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-144">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="d8ca4-145">Si noti che è necessario raggiungere due decisioni prima di definire il supporto dell'annullamento:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-145">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="d8ca4-146">La classe, incluse eventuali aggiunte future previste, include una sola operazione asincrona che supporta l'annullamento?</span><span class="sxs-lookup"><span data-stu-id="d8ca4-146">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="d8ca4-147">Le operazioni asincrone che supportano l'annullamento supportano più operazioni in sospeso?</span><span class="sxs-lookup"><span data-stu-id="d8ca4-147">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="d8ca4-148">Ovvero, il _metodo MethodName_**Async** accetta un `userState` parametro e consente più chiamate prima di attendere il completamento di qualsiasi?</span><span class="sxs-lookup"><span data-stu-id="d8ca4-148">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="d8ca4-149">Usare le risposte a queste due domande nella tabella seguente per determinare la firma per il metodo di annullamento scelto.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-149">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="d8ca4-150">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8ca4-150">Visual Basic</span></span>

||<span data-ttu-id="d8ca4-151">Più operazioni simultanee supportate</span><span class="sxs-lookup"><span data-stu-id="d8ca4-151">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="d8ca4-152">Una sola operazione alla volta</span><span class="sxs-lookup"><span data-stu-id="d8ca4-152">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="d8ca4-153">Una operazione asincrona nell'intera classe</span><span class="sxs-lookup"><span data-stu-id="d8ca4-153">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="d8ca4-154">Più operazioni asincrone nella classe</span><span class="sxs-lookup"><span data-stu-id="d8ca4-154">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="d8ca4-155">C\#</span><span class="sxs-lookup"><span data-stu-id="d8ca4-155">C\#</span></span>

||<span data-ttu-id="d8ca4-156">Più operazioni simultanee supportate</span><span class="sxs-lookup"><span data-stu-id="d8ca4-156">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="d8ca4-157">Una sola operazione alla volta</span><span class="sxs-lookup"><span data-stu-id="d8ca4-157">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="d8ca4-158">Una operazione asincrona nell'intera classe</span><span class="sxs-lookup"><span data-stu-id="d8ca4-158">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="d8ca4-159">Più operazioni asincrone nella classe</span><span class="sxs-lookup"><span data-stu-id="d8ca4-159">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="d8ca4-160">Se si definisce il metodo `CancelAsync(object userState)`, i client devono scegliere con cautela i valori di stato per permettere la distinzione tra tutti i metodi asincroni chiamati sull'oggetto e non solo tra tutte le chiamate di un singolo metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-160">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="d8ca4-161">La decisione di denominare la versione a singola operazione asincrona MethodName**AsyncCancel** si basa sulla possibilità di individuare più facilmente il metodo in un ambiente di progettazione come IntelliSense di Visual Studio.The decision to name the single-async-operation version _MethodName_is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-161">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="d8ca4-162">Questo raggruppa i membri correlati e li distingue dagli altri membri che non hanno a che fare con funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-162">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="d8ca4-163">Se si prevede che potrebbero essere aggiunte altre operazioni asincrone nelle versioni successive, è preferibile definire `CancelAsync`.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-163">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="d8ca4-164">Non definire più metodi della tabella precedente nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-164">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="d8ca4-165">Non avrebbe senso e creerebbe confusione nell'interfaccia della classe con un numero eccessivo di metodi.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-165">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="d8ca4-166">Questi metodi vengono in genere restituiti immediatamente e l'esito dell'operazione di annullamento non è garantito.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-166">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="d8ca4-167">Nel gestore eventi per il _MethodName_**Completed** evento, il `Cancelled` _MethodName_**CompletedEventArgs** oggetto contiene un campo, che i client possono utilizzare per determinare se si è verificato l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-167">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="d8ca4-168">Rispettare la semantica di annullamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-168">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="d8ca4-169">Supporto facoltativo della proprietà IsBusy</span><span class="sxs-lookup"><span data-stu-id="d8ca4-169">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="d8ca4-170">Se la classe non supporta più chiamate simultanee, è consigliabile esporre una proprietà `IsBusy`.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-170">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="d8ca4-171">Ciò consente agli sviluppatori di determinare se un _metodo MethodName_**Async** è in esecuzione senza intercettare un'eccezione dal metodo _MethodName_**Async.**</span><span class="sxs-lookup"><span data-stu-id="d8ca4-171">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="d8ca4-172">Rispettare la semantica di `IsBusy` descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-172">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="d8ca4-173">Supporto facoltativo per la generazione di report sullo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="d8ca4-173">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="d8ca4-174">È spesso utile che un'operazione asincrona generi un report sullo stato di avanzamento durante il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-174">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="d8ca4-175">Il modello asincrono basato su eventi offre linee guida a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-175">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="d8ca4-176">Definire facoltativamente un evento che verrà generato dall'operazione asincrona e chiamato sul thread appropriato.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-176">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="d8ca4-177">L'oggetto <xref:System.ComponentModel.ProgressChangedEventArgs> supporta un indicatore di stato con valori interi compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-177">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="d8ca4-178">Denominare l'evento come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-178">Name this event as follows:</span></span>

  - <span data-ttu-id="d8ca4-179">`ProgressChanged` se la classe dispone di più operazioni asincrone (o presumibilmente aumenterà per includere più operazioni asincrone nelle versioni future);</span><span class="sxs-lookup"><span data-stu-id="d8ca4-179">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="d8ca4-180">_NomeMetodo_**ProgressChanged** se la classe dispone di una singola operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-180">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="d8ca4-181">Questa scelta di denominazione è paragonabile a quella eseguita per il metodo di annullamento, come descritto nella sezione Supporto facoltativo dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-181">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="d8ca4-182">Questo evento deve usare la firma del delegato <xref:System.ComponentModel.ProgressChangedEventHandler> e la classe <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-182">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="d8ca4-183">In alternativa, se è possibile fornire un indicatore di stato più specifico per il dominio (ad esempio, byte letti e byte totali per un'operazione di download), è consigliabile definire una classe derivata di <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-183">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="d8ca4-184">Si noti che `ProgressChanged` esiste un solo evento o _MethodName_**ProgressChanged** per la classe, indipendentemente dal numero di metodi asincroni supportati.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-184">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="d8ca4-185">I client devono `userState` utilizzare l'oggetto passato ai metodi _MethodName_**Async** per distinguere tra gli aggiornamenti dello stato di avanzamento in più operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-185">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="d8ca4-186">In alcuni casi, più operazioni potrebbero supportare lo stato di avanzamento e restituire singolarmente un indicatore diverso.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-186">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="d8ca4-187">In questo caso, un singolo evento `ProgressChanged` non è appropriato ed è opportuno scegliere di supportare più eventi `ProgressChanged`.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-187">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="d8ca4-188">In questo caso utilizzare un modello di denominazione di NomeMetodo ProgressChanged per ogni _metodo MethodName Async.In_this case use a naming pattern of _MethodName_**ProgressChanged** for each MethodName**Async** method.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-188">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="d8ca4-189">Rispettare la semantica della generazione di report sullo stato di avanzamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-189">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="d8ca4-190">Supporto facoltativo per la restituzione di risultati incrementali</span><span class="sxs-lookup"><span data-stu-id="d8ca4-190">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="d8ca4-191">A volte un'operazione asincrona può restituire risultati incrementali prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-191">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="d8ca4-192">Per supportare questo scenario sono disponibili numerose opzioni.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-192">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="d8ca4-193">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-193">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="d8ca4-194">Classe con singola operazione</span><span class="sxs-lookup"><span data-stu-id="d8ca4-194">Single-operation Class</span></span>

<span data-ttu-id="d8ca4-195">Se la classe supporta solo una singola operazione asincrona e tale operazione è in grado di restituire risultati incrementali:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-195">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="d8ca4-196">Estendere <xref:System.ComponentModel.ProgressChangedEventArgs> il tipo per contenere i dati dei risultati incrementali e definire un evento _NomeMetodo_**ProgressChanged** con questi dati estesi.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-196">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="d8ca4-197">Generare questo _MethodName_**ProgressChanged** evento quando è presente un risultato incrementale da segnalare.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-197">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="d8ca4-198">Questa soluzione si applica in modo specifico a una classe a singola operazione asincrona perché non si verifica alcun problema con lo stesso evento che si verifica per restituire risultati incrementali su "tutte le operazioni", come il _NomeMetodo_**ProgressChanged** evento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-198">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="d8ca4-199">Classe con più operazioni con risultati incrementali omogenei</span><span class="sxs-lookup"><span data-stu-id="d8ca4-199">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="d8ca4-200">In questo caso, la classe supporta più metodi asincroni, ognuno dei quali è in grado di restituire risultati incrementali che avranno tutti lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-200">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="d8ca4-201">Seguire il modello descritto in precedenza per le classi con singola operazione, poiché la stessa struttura di <xref:System.EventArgs> è applicabile a tutti i risultati incrementali.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-201">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="d8ca4-202">Definire `ProgressChanged` un evento anziché un _evento ProgressChanged NomeMetodo,_**ProgressChanged** poiché si applica a più metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-202">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="d8ca4-203">Classe con più operazioni con risultati incrementali eterogenei</span><span class="sxs-lookup"><span data-stu-id="d8ca4-203">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="d8ca4-204">Se la classe supporta più metodi asincroni, ognuno dei quali restituisce un tipo diverso di dati, è consigliabile:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-204">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="d8ca4-205">Separare il report dei risultati incrementali dal report sullo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-205">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="d8ca4-206">Definire un evento**ProgressChanged** <xref:System.EventArgs> _nomeMetodo_separato con appropriato per ogni metodo asincrono per gestire i dati dei risultati incrementali di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-206">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="d8ca4-207">Chiamare il gestore eventi sul thread appropriato, come descritto in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-207">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="d8ca4-208">Gestione dei parametri Out e Ref nei metodi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-208">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="d8ca4-209">Sebbene l'uso di `out` e `ref` sia, in generale, sconsigliato in .NET Framework, ecco le regole da seguire quando sono presenti:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-209">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="d8ca4-210">Dato un metodo *MethodName* sincrono:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-210">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="d8ca4-211">`out`i parametri di *NomeMetodo* non devono far parte di _NomeMetodo_**Async**.</span><span class="sxs-lookup"><span data-stu-id="d8ca4-211">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="d8ca4-212">Al contrario, devono essere parte di _MethodName_**CompletedEventArgs** con lo stesso nome del relativo parametro equivalente in *NomeMetodo* (a meno che non sia presente un nome più appropriato).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-212">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="d8ca4-213">`ref`I parametri di *MethodName* devono essere visualizzati come parte di _MethodName_**Async**e come parte di _MethodName_**CompletedEventArgs** con lo stesso nome del relativo parametro equivalente in *NomeMetodo* (a meno che non esista un nome più appropriato).</span><span class="sxs-lookup"><span data-stu-id="d8ca4-213">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="d8ca4-214">Si consideri ad esempio di avere una situazione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-214">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="d8ca4-215">Il metodo asincrono e la relativa classe <xref:System.ComponentModel.AsyncCompletedEventArgs> avranno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d8ca4-215">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

```vb
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)

Public Class MethodNameCompletedEventArgs
    Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As Integer
    End Property
    Public ReadOnly Property Arg2() As String
    End Property
    Public ReadOnly Property Arg3() As String
    End Property
End Class
```

```csharp
public void MethodNameAsync(string arg1, string arg2);

public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
{
    public int Result { get; };
    public string Arg2 { get; };
    public string Arg3 { get; };
}
```

## <a name="see-also"></a><span data-ttu-id="d8ca4-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8ca4-216">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="d8ca4-217">Procedura: implementare un componente che supporta il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-217">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="d8ca4-218">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="d8ca4-218">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="d8ca4-219">Procedura: implementare un form che utilizza un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="d8ca4-219">How to: Implement a Form That Uses a Background Operation</span></span>](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="d8ca4-220">Quando implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-220">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="d8ca4-221">Suggerimenti per l'implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="d8ca4-221">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- <span data-ttu-id="d8ca4-222">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="d8ca4-222">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>
