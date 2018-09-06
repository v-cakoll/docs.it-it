---
title: Demux personalizzato
ms.date: 03/30/2017
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
ms.openlocfilehash: 1542743a6e1658bad162d7ee9ca73e6b9b0444e2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803421"
---
# <a name="custom-demux"></a><span data-ttu-id="934f1-102">Demux personalizzato</span><span class="sxs-lookup"><span data-stu-id="934f1-102">Custom Demux</span></span>
<span data-ttu-id="934f1-103">Questo esempio viene illustrato come le intestazioni dei messaggi MSMQ possono essere mappate alle operazioni del servizio diversi, in modo che i servizi Windows Communication Foundation (WCF) che utilizzano <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> non sono limitati all'uso di un'operazione del servizio come illustrato nel [ Accodamento messaggi in Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) e [Windows Communication Foundation a Accodamento messaggi](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) esempi.</span><span class="sxs-lookup"><span data-stu-id="934f1-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that Windows Communication Foundation (WCF) services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="934f1-104">Il servizio, in questo esempio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="934f1-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="934f1-105">Il contratto di servizio è `IOrderProcessor` e definisce un servizio unidirezionale adatto per l'uso con le code.</span><span class="sxs-lookup"><span data-stu-id="934f1-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 <span data-ttu-id="934f1-106">Un messaggio MSMQ non dispone di un'intestazione Action.</span><span class="sxs-lookup"><span data-stu-id="934f1-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="934f1-107">Non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi su contratti dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="934f1-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="934f1-108">Pertanto, può essere presente un solo contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="934f1-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="934f1-109">Per superare questa limitazione il servizio implementa il metodo <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> dell'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="934f1-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="934f1-110">Il metodo <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> consente al servizio di eseguire il mapping di una determinata intestazione del messaggio con una particolare operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="934f1-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="934f1-111">In questo esempio, l'intestazione dell'etichetta del messaggio è mappata sulle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="934f1-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="934f1-112">Il parametro `Name` del contratto dell'operazione determina quale operazione del servizio deve essere distribuita per una determinata etichetta del messaggio.</span><span class="sxs-lookup"><span data-stu-id="934f1-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="934f1-113">Ad esempio, se l'intestazione dell'etichetta del messaggio contiene "SubmitPurchaseOrder", viene richiamata l'operazione del servizio "SubmitPurchaseOrder".</span><span class="sxs-lookup"><span data-stu-id="934f1-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 <span data-ttu-id="934f1-114">Il servizio deve implementare il metodo <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> dell'interfaccia <xref:System.ServiceModel.Description.IContractBehavior> come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="934f1-115">Questo applica l'`OperationSelector` personalizzato al runtime di distribuzione del framework del servizio.</span><span class="sxs-lookup"><span data-stu-id="934f1-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 <span data-ttu-id="934f1-116">Prima di arrivare a OperationSelector, un messaggio deve passare attraverso il <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> del dispatcher.</span><span class="sxs-lookup"><span data-stu-id="934f1-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="934f1-117">Per impostazione predefinita un messaggio viene rifiutato se non è possibile trovare la relativa azione in alcun contratto implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="934f1-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="934f1-118">Per evitare questo controllo, viene implementato un <xref:System.ServiceModel.Description.IEndpointBehavior> denominato `MatchAllFilterBehavior`, che consente il passaggio di tutti i messaggi attraverso il `ContractFilter` applicando <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 <span data-ttu-id="934f1-119">Quando il servizio riceve un messaggio, l'operazione del servizio appropriata viene distribuita usando le informazioni fornite dall'intestazione dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="934f1-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="934f1-120">Il corpo del messaggio viene deserializzato in un oggetto `PurchaseOrder`, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 <span data-ttu-id="934f1-121">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="934f1-121">The service is self-hosted.</span></span> <span data-ttu-id="934f1-122">Quando si usa MSMQ, la coda usata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="934f1-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="934f1-123">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="934f1-123">This can be done manually or through code.</span></span> <span data-ttu-id="934f1-124">In questo esempio, il servizio contiene il codice necessario per verificare l'esistenza della coda e la crea se necessario.</span><span class="sxs-lookup"><span data-stu-id="934f1-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="934f1-125">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="934f1-125">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```

 <span data-ttu-id="934f1-126">Il nome della coda MSMQ è specificato in una sezione appSettings del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="934f1-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="934f1-127">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="934f1-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="934f1-128">L'indirizzo dell'endpoint WCF specifica uno schema MSMQ. FormatName e viene utilizzato localhost per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="934f1-128">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="934f1-129">Di seguito viene indicato lo schema di un indirizzo di coda formattato correttamente in base alle linee guida sull'indirizzamento dei nomi del formato MSMQ.</span><span class="sxs-lookup"><span data-stu-id="934f1-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="934f1-130">In questo esempio richiede l'installazione di [Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=95143).</span><span class="sxs-lookup"><span data-stu-id="934f1-130">This sample requires the installation of [Message Queuing](https://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="934f1-131">Avviare il servizio ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="934f1-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="934f1-132">Sul client viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="934f1-133">Nel servizio deve essere visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="934f1-134">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="934f1-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="934f1-135">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="934f1-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="934f1-136">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="934f1-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="934f1-137">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="934f1-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="934f1-138">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="934f1-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="934f1-139">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="934f1-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="934f1-140">Aprire Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="934f1-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="934f1-141">Espandere la **funzionalità** scheda.</span><span class="sxs-lookup"><span data-stu-id="934f1-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="934f1-142">Fare doppio clic su **code Private**e selezionare **New**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="934f1-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="934f1-143">Verificare i **transazionale** casella.</span><span class="sxs-lookup"><span data-stu-id="934f1-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="934f1-144">Immettere `ServiceModelSamplesTransacted` come il nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="934f1-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="934f1-145">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="934f1-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="934f1-146">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="934f1-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="934f1-147">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="934f1-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="934f1-148">Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="934f1-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="934f1-149">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="934f1-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="934f1-150">Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".</span><span class="sxs-lookup"><span data-stu-id="934f1-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="934f1-151">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="934f1-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="934f1-152">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="934f1-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="934f1-153">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="934f1-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="934f1-154">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="934f1-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="934f1-155">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="934f1-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="934f1-156">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="934f1-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="934f1-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="934f1-157">See Also</span></span>  
 [<span data-ttu-id="934f1-158">Accodamento in WCF</span><span class="sxs-lookup"><span data-stu-id="934f1-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="934f1-159">Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="934f1-159">Message Queuing</span></span>](https://go.microsoft.com/fwlink/?LinkId=95143)
