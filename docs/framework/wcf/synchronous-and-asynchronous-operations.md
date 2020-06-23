---
title: Operazioni sincrone e asincrone
description: Informazioni sull'implementazione e la chiamata di operazioni del servizio asincrone. I servizi e i client WCF possono utilizzare operazioni asincrone a due livelli dell'applicazione.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
ms.openlocfilehash: f52f2613c96c0149c330bb75f80c6738f8d41146
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245919"
---
# <a name="synchronous-and-asynchronous-operations"></a><span data-ttu-id="ba601-104">Operazioni sincrone e asincrone</span><span class="sxs-lookup"><span data-stu-id="ba601-104">Synchronous and Asynchronous Operations</span></span>
<span data-ttu-id="ba601-105">In questo argomento vengono illustrate l'implementazione e la chiamata delle operazioni del servizio asincrone.</span><span class="sxs-lookup"><span data-stu-id="ba601-105">This topic discusses implementing and calling asynchronous service operations.</span></span>  
  
 <span data-ttu-id="ba601-106">Molte applicazioni chiamano metodi in modo asincrono, poiché ciò consente all'applicazione di continuare a eseguire operazioni utili mentre viene effettuata la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ba601-106">Many applications call methods asynchronously because it enables the application to continue doing useful work while the method call runs.</span></span> <span data-ttu-id="ba601-107">I servizi e i client di Windows Communication Foundation (WCF) possono partecipare alle chiamate di operazioni asincrone a due livelli distinti dell'applicazione, assicurando alle applicazioni WCF più flessibilità per ottimizzare la velocità effettiva in modo equilibrato rispetto all'interattività.</span><span class="sxs-lookup"><span data-stu-id="ba601-107">Windows Communication Foundation (WCF) services and clients can participate in asynchronous operation calls at two distinct levels of the application, which provide WCF applications even more flexibility to maximize throughput balanced against interactivity.</span></span>  
  
## <a name="types-of-asynchronous-operations"></a><span data-ttu-id="ba601-108">Tipi di operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="ba601-108">Types of Asynchronous Operations</span></span>  
 <span data-ttu-id="ba601-109">In tutti i contratti di servizio in WCF, indipendentemente dai tipi di parametri e dai valori restituiti, vengono usati attributi WCF per specificare un particolare modello di scambio dei messaggi tra client e servizio.</span><span class="sxs-lookup"><span data-stu-id="ba601-109">All service contracts in WCF, no matter the parameters types and return values, use WCF attributes to specify a particular message exchange pattern between client and service.</span></span> <span data-ttu-id="ba601-110">WCF indirizza automaticamente i messaggi in ingresso e in uscita all'operazione del servizio o al codice client in esecuzione appropriato.</span><span class="sxs-lookup"><span data-stu-id="ba601-110">WCF automatically routes inbound and outbound messages to the appropriate service operation or running client code.</span></span>  
  
 <span data-ttu-id="ba601-111">Il client possiede solo il contratto di servizio, che specifica il modello di scambio dei messaggi per una particolare operazione.</span><span class="sxs-lookup"><span data-stu-id="ba601-111">The client possesses only the service contract, which specifies the message exchange pattern for a particular operation.</span></span> <span data-ttu-id="ba601-112">I client possono offrire allo sviluppatore qualsiasi modello di programmazione desiderato, purché venga rispettato il modello di scambio dei messaggi sottostante.</span><span class="sxs-lookup"><span data-stu-id="ba601-112">Clients can offer the developer any programming model they choose, so long as the underlying message exchange pattern is observed.</span></span> <span data-ttu-id="ba601-113">Anche i servizi possono quindi implementare le operazioni in qualsiasi modo, purché venga rispettato il modello dei messaggi specificato.</span><span class="sxs-lookup"><span data-stu-id="ba601-113">So, too, can services implement operations in any manner, so long as the specified message pattern is observed.</span></span>  
  
 <span data-ttu-id="ba601-114">L'indipendenza del contratto di servizio dall'implementazione del client o del servizio consente le forme seguenti di esecuzione asincrona nelle applicazioni WCF:</span><span class="sxs-lookup"><span data-stu-id="ba601-114">The independence of the service contract from either the service or client implementation enables the following forms of asynchronous execution in WCF applications:</span></span>  
  
- <span data-ttu-id="ba601-115">I client possono richiamare operazioni di richiesta/risposta in modo asincrono usando uno scambio di messaggi sincrono.</span><span class="sxs-lookup"><span data-stu-id="ba601-115">Clients can invoke request/response operations asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="ba601-116">I servizi possono implementare operazioni di richiesta/risposta in modo asincrono usando uno scambio di messaggi sincrono.</span><span class="sxs-lookup"><span data-stu-id="ba601-116">Services can implement a request/response operation asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="ba601-117">Gli scambi di messaggi possono essere unidirezionali, indipendentemente dall'implementazione del client o del servizio.</span><span class="sxs-lookup"><span data-stu-id="ba601-117">Message exchanges can be one-way, regardless of the implementation of the client or service.</span></span>  
  
### <a name="suggested-asynchronous-scenarios"></a><span data-ttu-id="ba601-118">Scenari asincroni suggeriti</span><span class="sxs-lookup"><span data-stu-id="ba601-118">Suggested Asynchronous Scenarios</span></span>  
 <span data-ttu-id="ba601-119">Usare un approccio asincrono nell'implementazione di un'operazione di servizio se tale implementazione effettua una chiamata di blocco, ad esempio effettuando le operazioni di I/O.</span><span class="sxs-lookup"><span data-stu-id="ba601-119">Use an asynchronous approach in a service operation implementation if the operation service implementation makes a blocking call, such as doing I/O work.</span></span> <span data-ttu-id="ba601-120">Quando si effettua l'implementazione di un'operazione asincrona, provare a chiamare i metodi e le operazioni asincrone per estendere il più possibile il percorso della chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="ba601-120">When you are in an asynchronous operation implementation, try to call asynchronous operations and methods to extend the asynchronous call path as far as possible.</span></span> <span data-ttu-id="ba601-121">Ad esempio chiamare l'opzione`BeginOperationTwo()` dall'interno di `BeginOperationOne()`.</span><span class="sxs-lookup"><span data-stu-id="ba601-121">For example, call a `BeginOperationTwo()` from within `BeginOperationOne()`.</span></span>  
  
- <span data-ttu-id="ba601-122">Usare un approccio asincrono in un'applicazione client o in un'applicazione chiamante nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="ba601-122">Use an asynchronous approach in a client or calling application in the following cases:</span></span>  
  
- <span data-ttu-id="ba601-123">Se si richiamano operazioni da un'applicazione di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="ba601-123">If you are invoking operations from a middle-tier application.</span></span> <span data-ttu-id="ba601-124">Per altre informazioni su questi scenari, vedere [Applicazioni client di livello intermedio](./feature-details/middle-tier-client-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ba601-124">(For more information about such scenarios, see [Middle-Tier Client Applications](./feature-details/middle-tier-client-applications.md).)</span></span>  
  
- <span data-ttu-id="ba601-125">Se si richiamano operazioni all'interno di una pagina ASP.NET, usare pagine asincrone.</span><span class="sxs-lookup"><span data-stu-id="ba601-125">If you are invoking operations within an ASP.NET page, use asynchronous pages.</span></span>  
  
- <span data-ttu-id="ba601-126">Se si richiamano operazioni da applicazioni a thread singolo, ad esempio Windows Forms o Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ba601-126">If you are invoking operations from any application that is single threaded, such as Windows Forms or Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="ba601-127">Se si usa il modello di chiamata asincrono basato su eventi, l'evento risultante viene generato sul thread UI, aggiungendo velocità di risposta all'applicazione senza che vi sia necessità di gestire più thread.</span><span class="sxs-lookup"><span data-stu-id="ba601-127">When using the event-based asynchronous calling model, the result event is raised on the UI thread, adding responsiveness to the application without requiring you to handle multiple threads yourself.</span></span>  
  
- <span data-ttu-id="ba601-128">Generalmente, se è possibile scegliere tra una chiamata sincrona e una asincrona, scegliere la seconda.</span><span class="sxs-lookup"><span data-stu-id="ba601-128">In general, if you have a choice between a synchronous and asynchronous call, choose the asynchronous call.</span></span>  
  
### <a name="implementing-an-asynchronous-service-operation"></a><span data-ttu-id="ba601-129">Implementazione di un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="ba601-129">Implementing an Asynchronous Service Operation</span></span>  
 <span data-ttu-id="ba601-130">Le operazioni asincrone possono essere implementate tramite uno dei tre metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba601-130">Asynchronous operations can be implemented by using one of the three following methods:</span></span>  
  
1. <span data-ttu-id="ba601-131">Modello asincrono basato su attività</span><span class="sxs-lookup"><span data-stu-id="ba601-131">The task-based asynchronous pattern</span></span>  
  
2. <span data-ttu-id="ba601-132">Modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="ba601-132">The event-based asynchronous pattern</span></span>  
  
3. <span data-ttu-id="ba601-133">Modello asincrono IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="ba601-133">The IAsyncResult asynchronous pattern</span></span>  
  
#### <a name="task-based-asynchronous-pattern"></a><span data-ttu-id="ba601-134">Modello asincrono basato su attività</span><span class="sxs-lookup"><span data-stu-id="ba601-134">Task-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="ba601-135">Il modello asincrono basato su attività è la modalità preferita per implementare le operazioni asincrone dal momento che è il più semplice.</span><span class="sxs-lookup"><span data-stu-id="ba601-135">The task-based asynchronous pattern is the preferred way to implement asynchronous operations because it is the easiest and most straight forward.</span></span> <span data-ttu-id="ba601-136">Per usare questo metodo, implementare semplicemente l'operazione del servizio e specificare un tipo restituito Task \<T> , dove T è il tipo restituito dall'operazione logica.</span><span class="sxs-lookup"><span data-stu-id="ba601-136">To use this method simply implement your service operation and specify a return type of Task\<T>, where T is the type returned by the logical operation.</span></span> <span data-ttu-id="ba601-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ba601-137">For example:</span></span>  
  
```csharp  
public class SampleService:ISampleService
{
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)
   {
      return Task<string>.Factory.StartNew(() =>
      {
         return msg;
      });
   }  
   // ...  
}  
```  
  
 <span data-ttu-id="ba601-138">L'operazione SampleMethodTaskAsync restituisce Task \<string> perché l'operazione logica restituisce una stringa.</span><span class="sxs-lookup"><span data-stu-id="ba601-138">The SampleMethodTaskAsync operation returns Task\<string> because the logical operation returns a string.</span></span> <span data-ttu-id="ba601-139">Per altre informazioni sul modello asincrono basato su attività, vedere [The Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=232504) (Modello asincrono basato su attività).</span><span class="sxs-lookup"><span data-stu-id="ba601-139">For more information about the task-based asynchronous pattern, see [The Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=232504).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ba601-140">Quando si usa il modello asincrono basato su attività, è possibile che venga generato un oggetto T: System.AggregateException se si verifica un'eccezione nell'attesa del completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ba601-140">When using the task-based asynchronous pattern, a T:System.AggregateException may be thrown if an exception occurs while waiting on the completion of the operation.</span></span> <span data-ttu-id="ba601-141">Questa eccezione può verificarsi nel client o nei servizi.</span><span class="sxs-lookup"><span data-stu-id="ba601-141">This exception may occur on the client or services</span></span>  
  
#### <a name="event-based-asynchronous-pattern"></a><span data-ttu-id="ba601-142">Modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="ba601-142">Event-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="ba601-143">Un servizio che supporta il modello asincrono basato su eventi disporrà di una o più operazioni denominate MethodNameAsync.</span><span class="sxs-lookup"><span data-stu-id="ba601-143">A service that supports the Event-based Asynchronous Pattern will have one or more operations named MethodNameAsync.</span></span> <span data-ttu-id="ba601-144">Tali metodi possono eseguire il mirroring delle versioni sincrone che eseguono la stessa operazione sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="ba601-144">These methods may mirror synchronous versions, which perform the same operation on the current thread.</span></span> <span data-ttu-id="ba601-145">La classe può anche disporre di un evento MethodNameCompleted e di un metodo MethodNameAsyncCancel (o semplicemente CancelAsync).</span><span class="sxs-lookup"><span data-stu-id="ba601-145">The class may also have a MethodNameCompleted event and it may have a MethodNameAsyncCancel (or simply CancelAsync) method.</span></span> <span data-ttu-id="ba601-146">Un client che desidera chiamare l'operazione definirà un gestore eventi da chiamare al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ba601-146">A client wishing to call the operation will define an event handler to be called when the operation completes,</span></span>  
  
 <span data-ttu-id="ba601-147">Nel frammento di codice riportato di seguito viene illustrato come dichiarare le operazioni asincrone mediante il modello asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="ba601-147">The following code snippet illustrates how to declare asynchronous operations using the event-based asynchronous pattern.</span></span>  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 <span data-ttu-id="ba601-148">Per altre informazioni sul modello asincrono basato su eventi, vedere [Cenni preliminari sul modello asincrono basato su eventi](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba601-148">For more information about the Event-based Asynchronous Pattern, see [The Event-Based Asynchronous Pattern](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
#### <a name="iasyncresult-asynchronous-pattern"></a><span data-ttu-id="ba601-149">Modello asincrono IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="ba601-149">IAsyncResult Asynchronous Pattern</span></span>  
 <span data-ttu-id="ba601-150">Un'operazione del servizio può essere implementata in modo asincrono usando il .NET Framework modello di programmazione asincrona e contrassegnando il `<Begin>` metodo con la <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> proprietà impostata su `true` .</span><span class="sxs-lookup"><span data-stu-id="ba601-150">A service operation can be implemented in an asynchronous fashion using the .NET Framework asynchronous programming pattern and marking the `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true`.</span></span> <span data-ttu-id="ba601-151">In questo caso, l'operazione asincrona viene esposta nei metadati nella stessa forma di un'operazione sincrona, ovvero come singola operazione con un messaggio di richiesta e un messaggio di risposta correlato.</span><span class="sxs-lookup"><span data-stu-id="ba601-151">In this case, the asynchronous operation is exposed in metadata in the same form as a synchronous operation: It is exposed as a single operation with a request message and a correlated response message.</span></span> <span data-ttu-id="ba601-152">I modelli di programmazione client possono quindi effettuare una scelta.</span><span class="sxs-lookup"><span data-stu-id="ba601-152">Client programming models then have a choice.</span></span> <span data-ttu-id="ba601-153">Possono rappresentare questo modello come operazione sincrona o asincrona, a condizione che, quando viene richiamato il servizio, si verifichi uno scambio di messaggi di richiesta-risposta.</span><span class="sxs-lookup"><span data-stu-id="ba601-153">They can represent this pattern as a synchronous operation or as an asynchronous one, so long as when the service is invoked a request-response message exchange takes place.</span></span>  
  
 <span data-ttu-id="ba601-154">In generale, data la natura asincrona dei sistemi, non è necessario considerare una dipendenza sui thread.</span><span class="sxs-lookup"><span data-stu-id="ba601-154">In general, with the asynchronous nature of the systems, you should not take a dependency on the threads.</span></span>  <span data-ttu-id="ba601-155">Il modo più affidabile di passare dati alle varie fasi di elaborazione di distribuzione dell'operazione è rappresentato dall'uso di estensioni.</span><span class="sxs-lookup"><span data-stu-id="ba601-155">The most reliable way of passing data to various stages of operation dispatch processing is to use extensions.</span></span>  
  
 <span data-ttu-id="ba601-156">Per un esempio, vedere [Procedura: Implementare un'operazione del servizio asincrona](how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="ba601-156">For an example, see [How to: Implement an Asynchronous Service Operation](how-to-implement-an-asynchronous-service-operation.md).</span></span>  
  
 <span data-ttu-id="ba601-157">Per definire un'operazione di contratto `X` eseguita in modo asincrono indipendentemente dalla modalità con cui viene chiamata nell'applicazione client:</span><span class="sxs-lookup"><span data-stu-id="ba601-157">To define a contract operation `X` that is executed asynchronously regardless of how it is called in the client application:</span></span>  
  
- <span data-ttu-id="ba601-158">Definire due metodi usando il modello `BeginOperation` e `EndOperation`.</span><span class="sxs-lookup"><span data-stu-id="ba601-158">Define two methods using the pattern `BeginOperation` and `EndOperation`.</span></span>  
  
- <span data-ttu-id="ba601-159">Il metodo `BeginOperation` include i parametri `in` e `ref` per l'operazione e restituisce un tipo <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="ba601-159">The `BeginOperation` method includes `in` and `ref` parameters for the operation and returns an <xref:System.IAsyncResult> type.</span></span>  
  
- <span data-ttu-id="ba601-160">Il metodo `EndOperation` include un parametro <xref:System.IAsyncResult>, nonché i parametri `out` e `ref`, e restituisce il tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="ba601-160">The `EndOperation` method includes an <xref:System.IAsyncResult> parameter as well as the `out` and `ref` parameters and returns the operations return type.</span></span>  
  
 <span data-ttu-id="ba601-161">Vedere, ad esempio, il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="ba601-161">For example, see the following method.</span></span>  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 <span data-ttu-id="ba601-162">Per creare un'operazione asincrona, i due metodi sarebbero:</span><span class="sxs-lookup"><span data-stu-id="ba601-162">To create an asynchronous operation, the two methods would be:</span></span>  
  
```csharp  
[OperationContract(AsyncPattern=true)]
IAsyncResult BeginDoWork(string data,
                         ref string inout,
                         AsyncCallback callback,
                         object state);
int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>
Function BeginDoWork(ByVal data As String, _
                     ByRef inout As String, _
                     ByVal callback As AsyncCallback, _
                     ByVal state As Object) As IAsyncResult
Function EndDoWork(ByRef inout As String, ByRef outonly As String, ByVal result As IAsyncResult) As Integer  
```  
  
> [!NOTE]
> <span data-ttu-id="ba601-163">L'attributo <xref:System.ServiceModel.OperationContractAttribute> viene applicato solo al metodo `BeginDoWork`.</span><span class="sxs-lookup"><span data-stu-id="ba601-163">The <xref:System.ServiceModel.OperationContractAttribute> attribute is applied only to the `BeginDoWork` method.</span></span> <span data-ttu-id="ba601-164">Il contratto risultante include un'operazione WSDL denominata `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="ba601-164">The resulting contract has one WSDL operation named `DoWork`.</span></span>  
  
### <a name="client-side-asynchronous-invocations"></a><span data-ttu-id="ba601-165">Chiamate asincrone lato client</span><span class="sxs-lookup"><span data-stu-id="ba601-165">Client-Side Asynchronous Invocations</span></span>  
 <span data-ttu-id="ba601-166">Un'applicazione client WCF può usare uno qualsiasi dei tre modelli di chiamata asincrona descritti in precedenza</span><span class="sxs-lookup"><span data-stu-id="ba601-166">A WCF client application can use any of three asynchronous calling models described previously</span></span>  
  
 <span data-ttu-id="ba601-167">Quando si usa il modello basato su attività, chiamare semplicemente l'operazione usando la parola chiave await come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="ba601-167">When using the task-based model, simply call the operation using the await keyword as shown in the following code snippet.</span></span>  
  
```csharp  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 <span data-ttu-id="ba601-168">L'uso del modello asincrono basato su eventi richiede solamente l'aggiunta di un gestore eventi per ricevere una notifica di risposta e l'evento risultante viene automaticamente generato sul thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ba601-168">Using the event-based asynchronous pattern only requires adding an event handler to receive a notification of the response -- and the resulting event is raised on the user interface thread automatically.</span></span> <span data-ttu-id="ba601-169">Per usare questo approccio, specificare entrambe le opzioni di comando **/async** e **/tcv:Version35** con lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ba601-169">To use this approach, specify both the **/async** and **/tcv:Version35** command options with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 <span data-ttu-id="ba601-170">Al termine di questa operazione, Svcutil.exe genera una classe client WCF in cui l'infrastruttura dell'evento consente all'applicazione chiamante di implementare e fare in modo che un gestore eventi riceva la risposta ed esegua le operazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ba601-170">When this is done, Svcutil.exe generates a WCF client class with the event infrastructure that enables the calling application to implement and assign an event handler to receive the response and take the appropriate action.</span></span> <span data-ttu-id="ba601-171">Per un esempio completo, vedere [Procedura: Chiamare operazioni del servizio in modo asincrono](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="ba601-171">For a complete example, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
 <span data-ttu-id="ba601-172">Il modello asincrono basato su eventi, tuttavia, è disponibile solo in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="ba601-172">The event-based asynchronous model, however, is only available in .NET Framework 3.5.</span></span> <span data-ttu-id="ba601-173">Inoltre, non è supportato neanche in .NET Framework 3,5 quando viene creato un canale client WCF utilizzando un oggetto <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ba601-173">In addition, it is not supported even in .NET Framework 3.5 when a WCF client channel is created by using a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ba601-174">Con gli oggetti del canale client WCF, per richiamare le operazioni in modo asincrono è necessario usare oggetti <xref:System.IAsyncResult?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba601-174">With WCF client channel objects, you must use <xref:System.IAsyncResult?displayProperty=nameWithType> objects to invoke your operations asynchronously.</span></span> <span data-ttu-id="ba601-175">Per usare questo approccio, specificare l'opzione di comando **/async** con lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ba601-175">To use this approach, specify the **/async** command option with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async
```  
  
 <span data-ttu-id="ba601-176">In questo modo viene generato un contratto di servizio nel quale ciascuna operazione viene modellata come un metodo `<Begin>` con la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> impostata su `true` e un metodo `<End>` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ba601-176">This generates a service contract in which each operation is modeled as a `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true` and a corresponding `<End>` method.</span></span> <span data-ttu-id="ba601-177">Per un esempio completo dell'uso di <xref:System.ServiceModel.ChannelFactory%601>, vedere [Procedura: Chiamare operazioni in modo asincrono tramite una factory canale](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="ba601-177">For a complete example using a <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
 <span data-ttu-id="ba601-178">In ogni caso, le applicazioni possono richiamare un'operazione in modo asincrono anche se il servizio viene implementato in modo sincrono, esattamente come un'applicazione può usare lo stesso modello per richiamare in modo asincrono un metodo sincrono locale.</span><span class="sxs-lookup"><span data-stu-id="ba601-178">In either case, applications can invoke an operation asynchronously even if the service is implemented synchronously, in the same way that an application can use the same pattern to invoke asynchronously a local synchronous method.</span></span> <span data-ttu-id="ba601-179">La modalità di implementazione dell'operazione non è significativa per il client. Quando il messaggio di risposta arriva, il relativo contenuto viene inviato al metodo asincrono <> del client `End` e il client recupera le informazioni.</span><span class="sxs-lookup"><span data-stu-id="ba601-179">How the operation is implemented is not significant to the client; when the response message arrives, its content is dispatched to the client's asynchronous <`End`> method and the client retrieves the information.</span></span>  
  
### <a name="one-way-message-exchange-patterns"></a><span data-ttu-id="ba601-180">Modelli di scambio di messaggi unidirezionali</span><span class="sxs-lookup"><span data-stu-id="ba601-180">One-Way Message Exchange Patterns</span></span>  
 <span data-ttu-id="ba601-181">È inoltre possibile creare un modello di scambio di messaggi asincrono, in cui le operazioni unidirezionali (operazioni per cui se la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> è `true` non esiste una risposta correlata) possono essere inviate in entrambe le direzioni dal client o dal servizio in modo indipendente dall'altro lato.</span><span class="sxs-lookup"><span data-stu-id="ba601-181">You can also create an asynchronous message exchange pattern in which one-way operations (operations for which the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> is `true` have no correlated response) can be sent in either direction by the client or service independently of the other side.</span></span> <span data-ttu-id="ba601-182">(Viene utilizzato il modello di scambio di messaggi duplex con messaggi unidirezionali). In questo caso, il contratto di servizio specifica un scambio di messaggi unidirezionale che può essere implementato da entrambi i lati come chiamate o implementazioni asincrone, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="ba601-182">(This uses the duplex message exchange pattern with one-way messages.) In this case, the service contract specifies a one-way message exchange that either side can implement as asynchronous calls or implementations, or not, as appropriate.</span></span> <span data-ttu-id="ba601-183">In genere, quando il contratto è uno scambio di messaggi unidirezionali, le implementazioni possono essere prevalentemente asincrone poiché, una volta inviato un messaggio, l'applicazione non attende una risposta e può continuare a svolgere altre attività.</span><span class="sxs-lookup"><span data-stu-id="ba601-183">Generally, when the contract is an exchange of one-way messages, the implementations can largely be asynchronous because once a message is sent the application does not wait for a reply and can continue doing other work.</span></span>  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a><span data-ttu-id="ba601-184">Contratti client e di messaggio asincroni basati su eventi</span><span class="sxs-lookup"><span data-stu-id="ba601-184">Event-based Asynchronous Clients and Message Contracts</span></span>  
 <span data-ttu-id="ba601-185">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ba601-185">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ba601-186">Di conseguenza, è possibile che, se un client importa metadati usando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ba601-186">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="ba601-187">Se si vuole ricevere l'oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in tale oggetto, usare l'opzione di comando **/messageContract**.</span><span class="sxs-lookup"><span data-stu-id="ba601-187">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the **/messageContract** command option.</span></span> <span data-ttu-id="ba601-188">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ba601-188">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ba601-189">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="ba601-189">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba601-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba601-190">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
