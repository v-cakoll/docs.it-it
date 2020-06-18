---
title: Implementazione del modello asincrono basato su eventi
description: Informazioni su come implementare il modello asincrono basato su eventi (EAP) in .NET. EAP è un modo standard per creare un pacchetto di una classe con funzionalità asincrone.
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
ms.openlocfilehash: e36ae21e1e03c8c5c688b7446f660ab1bb666a94
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904377"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="95c45-104">Implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-104">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="95c45-105">Se si scrive una classe con alcune operazioni che possono causare ritardi evidenti, è consigliabile assegnarle funzionalità asincrone implementando il [modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-105">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="95c45-106">Il modello asincrono basato su eventi offre un modo standardizzato per aggiungere funzionalità asincrone a una classe.</span><span class="sxs-lookup"><span data-stu-id="95c45-106">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="95c45-107">Se implementata con classi helper come <xref:System.ComponentModel.AsyncOperationManager>, la classe funzionerà con qualsiasi modello di applicazione, tra cui ASP.NET, applicazioni console e Windows Forms Application.</span><span class="sxs-lookup"><span data-stu-id="95c45-107">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="95c45-108">Per un esempio che implementa il modello asincrono basato su eventi, vedere [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-108">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="95c45-109">Per operazioni asincrone semplici, può risultare idoneo il componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="95c45-109">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="95c45-110">Per altre informazioni su <xref:System.ComponentModel.BackgroundWorker>, vedere [Procedura: eseguire un'operazione in background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-110">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="95c45-111">L'elenco seguente descrive le funzionalità del modello asincrono basato su eventi affrontate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="95c45-111">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="95c45-112">Opportunità per implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-112">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="95c45-113">Denominazione di metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="95c45-113">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="95c45-114">Supporto facoltativo dell'annullamento</span><span class="sxs-lookup"><span data-stu-id="95c45-114">Optionally Support Cancellation</span></span>

- <span data-ttu-id="95c45-115">Supporto facoltativo della proprietà IsBusy</span><span class="sxs-lookup"><span data-stu-id="95c45-115">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="95c45-116">Supporto facoltativo per la generazione di report sullo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="95c45-116">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="95c45-117">Supporto facoltativo per la restituzione di risultati incrementali</span><span class="sxs-lookup"><span data-stu-id="95c45-117">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="95c45-118">Gestione dei parametri Out e Ref nei metodi</span><span class="sxs-lookup"><span data-stu-id="95c45-118">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="95c45-119">Opportunità per implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-119">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="95c45-120">Valutare l'implementazione del modello asincrono basato su eventi quando:</span><span class="sxs-lookup"><span data-stu-id="95c45-120">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="95c45-121">I client della classe non richiedono che siano disponibili oggetti <xref:System.Threading.WaitHandle> e <xref:System.IAsyncResult> per le operazioni asincrone, quindi il polling e il metodo <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> devono essere compilati dal client.</span><span class="sxs-lookup"><span data-stu-id="95c45-121">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="95c45-122">Si desidera che le operazioni asincrone vengano gestite dal client con il modello noto di evento/delegato.</span><span class="sxs-lookup"><span data-stu-id="95c45-122">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="95c45-123">Qualsiasi operazione è un candidato per un'implementazione asincrona, ma è opportuno considerare quelle con lunghe latenze previste.</span><span class="sxs-lookup"><span data-stu-id="95c45-123">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="95c45-124">Sono particolarmente indicate le operazioni in cui i client chiamano un metodo e ricevono una notifica al completamento, senza richiedere ulteriori interventi.</span><span class="sxs-lookup"><span data-stu-id="95c45-124">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="95c45-125">Rientrano in questa condizione anche le operazioni con esecuzione continua,che inviano notifiche periodiche ai client sullo stato di avanzamento, sui risultati incrementali o sulle modifiche di stato.</span><span class="sxs-lookup"><span data-stu-id="95c45-125">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="95c45-126">Per altre informazioni sui casi in cui supportare il modello asincrono basato su eventi, vedere [Quando implementare il modello asincrono basato su eventi](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-126">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="95c45-127">Denominazione di metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="95c45-127">Naming Asynchronous Methods</span></span>

<span data-ttu-id="95c45-128">Per ogni metodo *MethodName* sincrono per il quale si desidera specificare una controparte asincrona:</span><span class="sxs-lookup"><span data-stu-id="95c45-128">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="95c45-129">Definire un metodo**Async** _MethodName_che:</span><span class="sxs-lookup"><span data-stu-id="95c45-129">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="95c45-130">Restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="95c45-130">Returns `void`.</span></span>

- <span data-ttu-id="95c45-131">Accetta gli stessi parametri del metodo *MethodName*.</span><span class="sxs-lookup"><span data-stu-id="95c45-131">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="95c45-132">Accetta più chiamate.</span><span class="sxs-lookup"><span data-stu-id="95c45-132">Accepts multiple invocations.</span></span>

<span data-ttu-id="95c45-133">Definire facoltativamente un overload**Async** di _MethodName_, identico a _MethodName_**Async**, ma con un parametro con valori di oggetto aggiuntivo denominato `userState` .</span><span class="sxs-lookup"><span data-stu-id="95c45-133">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="95c45-134">Seguire questa procedura se si intende gestire più chiamate simultanee del metodo, nel qual caso il valore `userState` verrà recapitato nuovamente a tutti i gestori eventi per distinguere le chiamate del metodo.</span><span class="sxs-lookup"><span data-stu-id="95c45-134">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="95c45-135">È anche possibile scegliere questa opzione come posizione in cui archiviare lo stato utente per un successivo recupero.</span><span class="sxs-lookup"><span data-stu-id="95c45-135">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="95c45-136">Per ogni firma del metodo**Async** _MethodName_separato:</span><span class="sxs-lookup"><span data-stu-id="95c45-136">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="95c45-137">Definire l'evento seguente nella stessa classe del metodo:</span><span class="sxs-lookup"><span data-stu-id="95c45-137">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="95c45-138">Definire il delegato seguente e <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="95c45-138">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="95c45-139">che verranno probabilmente definiti all'esterno della classe, ma nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="95c45-139">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

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

    - <span data-ttu-id="95c45-140">Assicurarsi che la classe _MethodName_**CompletedEventArgs** esponga i relativi membri come proprietà di sola lettura e non come campi, poiché i campi impediscono Data Binding.</span><span class="sxs-lookup"><span data-stu-id="95c45-140">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="95c45-141">Non definire alcuna classe derivata da <xref:System.ComponentModel.AsyncCompletedEventArgs> per i metodi che non producono risultati.</span><span class="sxs-lookup"><span data-stu-id="95c45-141">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="95c45-142">Usare semplicemente un'istanza di <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="95c45-142">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="95c45-143">È perfettamente accettabile, quando possibile e appropriato, riutilizzare il delegato e i tipi <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="95c45-143">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="95c45-144">In questo caso, la denominazione non sarà coerente con il nome del metodo, perché un delegato e un oggetto <xref:System.ComponentModel.AsyncCompletedEventArgs> specifici non saranno associati a un singolo metodo.</span><span class="sxs-lookup"><span data-stu-id="95c45-144">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="95c45-145">Supporto facoltativo dell'annullamento</span><span class="sxs-lookup"><span data-stu-id="95c45-145">Optionally Support Cancellation</span></span>

<span data-ttu-id="95c45-146">Se la classe supporta l'annullamento delle operazioni asincrone, l'annullamento dovrebbe essere esposto al client come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="95c45-146">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="95c45-147">Si noti che è necessario raggiungere due decisioni prima di definire il supporto dell'annullamento:</span><span class="sxs-lookup"><span data-stu-id="95c45-147">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="95c45-148">La classe, incluse eventuali aggiunte future previste, include una sola operazione asincrona che supporta l'annullamento?</span><span class="sxs-lookup"><span data-stu-id="95c45-148">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="95c45-149">Le operazioni asincrone che supportano l'annullamento supportano più operazioni in sospeso?</span><span class="sxs-lookup"><span data-stu-id="95c45-149">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="95c45-150">In altre termini, il metodo**Async** _Method_accetta un `userState` parametro e consente più chiamate prima di attendere il completamento di qualsiasi?</span><span class="sxs-lookup"><span data-stu-id="95c45-150">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="95c45-151">Usare le risposte a queste due domande nella tabella seguente per determinare la firma per il metodo di annullamento scelto.</span><span class="sxs-lookup"><span data-stu-id="95c45-151">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="95c45-152">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95c45-152">Visual Basic</span></span>

||<span data-ttu-id="95c45-153">Più operazioni simultanee supportate</span><span class="sxs-lookup"><span data-stu-id="95c45-153">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="95c45-154">Una sola operazione alla volta</span><span class="sxs-lookup"><span data-stu-id="95c45-154">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="95c45-155">Una operazione asincrona nell'intera classe</span><span class="sxs-lookup"><span data-stu-id="95c45-155">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="95c45-156">Più operazioni asincrone nella classe</span><span class="sxs-lookup"><span data-stu-id="95c45-156">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="95c45-157">C\#</span><span class="sxs-lookup"><span data-stu-id="95c45-157">C\#</span></span>

||<span data-ttu-id="95c45-158">Più operazioni simultanee supportate</span><span class="sxs-lookup"><span data-stu-id="95c45-158">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="95c45-159">Una sola operazione alla volta</span><span class="sxs-lookup"><span data-stu-id="95c45-159">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="95c45-160">Una operazione asincrona nell'intera classe</span><span class="sxs-lookup"><span data-stu-id="95c45-160">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="95c45-161">Più operazioni asincrone nella classe</span><span class="sxs-lookup"><span data-stu-id="95c45-161">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="95c45-162">Se si definisce il metodo `CancelAsync(object userState)`, i client devono scegliere con cautela i valori di stato per permettere la distinzione tra tutti i metodi asincroni chiamati sull'oggetto e non solo tra tutte le chiamate di un singolo metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="95c45-162">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="95c45-163">La decisione di denominare la versione single-Async-Operation _MethodName_**AsyncCancel** si basa sulla possibilità di individuare più facilmente il metodo in un ambiente di progettazione come IntelliSense di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="95c45-163">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="95c45-164">Questo raggruppa i membri correlati e li distingue dagli altri membri che non hanno a che fare con funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="95c45-164">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="95c45-165">Se si prevede che potrebbero essere aggiunte altre operazioni asincrone nelle versioni successive, è preferibile definire `CancelAsync`.</span><span class="sxs-lookup"><span data-stu-id="95c45-165">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="95c45-166">Non definire più metodi della tabella precedente nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="95c45-166">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="95c45-167">Non avrebbe senso e creerebbe confusione nell'interfaccia della classe con un numero eccessivo di metodi.</span><span class="sxs-lookup"><span data-stu-id="95c45-167">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="95c45-168">Questi metodi vengono in genere restituiti immediatamente e l'esito dell'operazione di annullamento non è garantito.</span><span class="sxs-lookup"><span data-stu-id="95c45-168">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="95c45-169">Nel gestore eventi per l'evento _MethodName_**Completed** , l'oggetto _NomeMetodo_**CompletedEventArgs** contiene un `Cancelled` campo, che i client possono usare per determinare se si è verificato l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="95c45-169">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="95c45-170">Rispettare la semantica di annullamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-170">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="95c45-171">Supporto facoltativo della proprietà IsBusy</span><span class="sxs-lookup"><span data-stu-id="95c45-171">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="95c45-172">Se la classe non supporta più chiamate simultanee, è consigliabile esporre una proprietà `IsBusy`.</span><span class="sxs-lookup"><span data-stu-id="95c45-172">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="95c45-173">Ciò consente agli sviluppatori di determinare se un metodo**Async** _MethodName_è in esecuzione senza intercettare un'eccezione dal metodo**Async** _MethodName_.</span><span class="sxs-lookup"><span data-stu-id="95c45-173">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="95c45-174">Rispettare la semantica di `IsBusy` descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-174">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="95c45-175">Supporto facoltativo per la generazione di report sullo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="95c45-175">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="95c45-176">È spesso utile che un'operazione asincrona generi un report sullo stato di avanzamento durante il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="95c45-176">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="95c45-177">Il modello asincrono basato su eventi offre linee guida a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="95c45-177">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="95c45-178">Definire facoltativamente un evento che verrà generato dall'operazione asincrona e chiamato sul thread appropriato.</span><span class="sxs-lookup"><span data-stu-id="95c45-178">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="95c45-179">L'oggetto <xref:System.ComponentModel.ProgressChangedEventArgs> supporta un indicatore di stato con valori interi compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="95c45-179">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="95c45-180">Denominare l'evento come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="95c45-180">Name this event as follows:</span></span>

  - <span data-ttu-id="95c45-181">`ProgressChanged` se la classe dispone di più operazioni asincrone (o presumibilmente aumenterà per includere più operazioni asincrone nelle versioni future);</span><span class="sxs-lookup"><span data-stu-id="95c45-181">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="95c45-182">_MethodName_**ProgressChanged** se la classe dispone di una singola operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="95c45-182">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="95c45-183">Questa scelta di denominazione è paragonabile a quella eseguita per il metodo di annullamento, come descritto nella sezione Supporto facoltativo dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="95c45-183">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="95c45-184">Questo evento deve usare la firma del delegato <xref:System.ComponentModel.ProgressChangedEventHandler> e la classe <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="95c45-184">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="95c45-185">In alternativa, se è possibile fornire un indicatore di stato più specifico per il dominio (ad esempio, byte letti e byte totali per un'operazione di download), è consigliabile definire una classe derivata di <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="95c45-185">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="95c45-186">Si noti che per la classe è presente un solo `ProgressChanged` evento o _MethodName_**ProgressChanged** , indipendentemente dal numero di metodi asincroni supportati.</span><span class="sxs-lookup"><span data-stu-id="95c45-186">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="95c45-187">Si prevede che i client usino l' `userState` oggetto passato ai metodi async _MethodName_**Async** per distinguere tra gli aggiornamenti dello stato di avanzamento in più operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="95c45-187">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="95c45-188">In alcuni casi, più operazioni potrebbero supportare lo stato di avanzamento e restituire singolarmente un indicatore diverso.</span><span class="sxs-lookup"><span data-stu-id="95c45-188">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="95c45-189">In questo caso, un singolo evento `ProgressChanged` non è appropriato ed è opportuno scegliere di supportare più eventi `ProgressChanged`.</span><span class="sxs-lookup"><span data-stu-id="95c45-189">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="95c45-190">In questo caso usare un modello di denominazione di _MethodName_**ProgressChanged** per ogni metodo**Async** _MethodName_.</span><span class="sxs-lookup"><span data-stu-id="95c45-190">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="95c45-191">Rispettare la semantica della generazione di report sullo stato di avanzamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-191">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="95c45-192">Supporto facoltativo per la restituzione di risultati incrementali</span><span class="sxs-lookup"><span data-stu-id="95c45-192">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="95c45-193">A volte un'operazione asincrona può restituire risultati incrementali prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="95c45-193">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="95c45-194">Per supportare questo scenario sono disponibili numerose opzioni.</span><span class="sxs-lookup"><span data-stu-id="95c45-194">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="95c45-195">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="95c45-195">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="95c45-196">Classe con singola operazione</span><span class="sxs-lookup"><span data-stu-id="95c45-196">Single-operation Class</span></span>

<span data-ttu-id="95c45-197">Se la classe supporta solo una singola operazione asincrona e tale operazione è in grado di restituire risultati incrementali:</span><span class="sxs-lookup"><span data-stu-id="95c45-197">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="95c45-198">Estendere il <xref:System.ComponentModel.ProgressChangedEventArgs> tipo per includere i dati del risultato incrementale e definire un evento _MethodName_**ProgressChanged** con i dati estesi.</span><span class="sxs-lookup"><span data-stu-id="95c45-198">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="95c45-199">Generare questo evento _MethodName_**ProgressChanged** quando è presente un risultato incrementale da segnalare.</span><span class="sxs-lookup"><span data-stu-id="95c45-199">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="95c45-200">Questa soluzione si applica in modo specifico a una classe con singola operazione asincrona poiché non si verificano problemi con lo stesso evento che si verifica per restituire i risultati incrementali in "tutte le operazioni", come fa l'evento _MethodName_**ProgressChanged** .</span><span class="sxs-lookup"><span data-stu-id="95c45-200">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="95c45-201">Classe con più operazioni con risultati incrementali omogenei</span><span class="sxs-lookup"><span data-stu-id="95c45-201">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="95c45-202">In questo caso, la classe supporta più metodi asincroni, ognuno dei quali è in grado di restituire risultati incrementali che avranno tutti lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="95c45-202">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="95c45-203">Seguire il modello descritto in precedenza per le classi con singola operazione, poiché la stessa struttura di <xref:System.EventArgs> è applicabile a tutti i risultati incrementali.</span><span class="sxs-lookup"><span data-stu-id="95c45-203">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="95c45-204">Definire un `ProgressChanged` evento anziché un evento _MethodName_**ProgressChanged** , poiché si applica a più metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="95c45-204">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="95c45-205">Classe con più operazioni con risultati incrementali eterogenei</span><span class="sxs-lookup"><span data-stu-id="95c45-205">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="95c45-206">Se la classe supporta più metodi asincroni, ognuno dei quali restituisce un tipo diverso di dati, è consigliabile:</span><span class="sxs-lookup"><span data-stu-id="95c45-206">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="95c45-207">Separare il report dei risultati incrementali dal report sullo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="95c45-207">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="95c45-208">Definire un evento _MethodName_**ProgressChanged** separato con appropriato <xref:System.EventArgs> per ogni metodo asincrono per gestire i dati dei risultati incrementali del metodo.</span><span class="sxs-lookup"><span data-stu-id="95c45-208">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="95c45-209">Chiamare il gestore eventi sul thread appropriato, come descritto in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="95c45-209">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="95c45-210">Gestione dei parametri Out e Ref nei metodi</span><span class="sxs-lookup"><span data-stu-id="95c45-210">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="95c45-211">Sebbene l'uso di `out` e `ref` sia, in generale, sconsigliato in .NET Framework, ecco le regole da seguire quando sono presenti:</span><span class="sxs-lookup"><span data-stu-id="95c45-211">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="95c45-212">Dato un metodo *MethodName* sincrono:</span><span class="sxs-lookup"><span data-stu-id="95c45-212">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="95c45-213">`out`i parametri per *MethodName* non devono far parte di _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="95c45-213">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="95c45-214">Devono invece far parte di _MethodName_**CompletedEventArgs** con lo stesso nome del relativo parametro equivalente in *MethodName* (a meno che non esista un nome più appropriato).</span><span class="sxs-lookup"><span data-stu-id="95c45-214">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="95c45-215">`ref`i parametri per *MethodName* devono essere visualizzati come parte di _MethodName_**Async**e come parte di _MethodName_**CompletedEventArgs** con lo stesso nome del relativo parametro equivalente in *MethodName* (a meno che non esista un nome più appropriato).</span><span class="sxs-lookup"><span data-stu-id="95c45-215">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="95c45-216">Si consideri ad esempio di avere una situazione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="95c45-216">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="95c45-217">Il metodo asincrono e la relativa classe <xref:System.ComponentModel.AsyncCompletedEventArgs> avranno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="95c45-217">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="95c45-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c45-218">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="95c45-219">Procedura: implementare un componente che supporta il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-219">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="95c45-220">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="95c45-220">How to: Run an Operation in the Background</span></span>](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="95c45-221">Procedura: implementare un form che utilizza un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="95c45-221">How to: Implement a Form That Uses a Background Operation</span></span>](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="95c45-222">Quando implementare il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-222">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="95c45-223">Suggerimenti per l'implementazione del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="95c45-223">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- <span data-ttu-id="95c45-224">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="95c45-224">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md)</span></span>
