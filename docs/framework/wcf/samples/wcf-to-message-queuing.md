---
title: Da Windows Communication Foundation a Accodamento messaggi
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: beb4382d61804e9b9ea12e1d191f3e96a637f871
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094800"
---
# <a name="windows-communication-foundation-to-message-queuing"></a><span data-ttu-id="64635-102">Da Windows Communication Foundation a Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="64635-102">Windows Communication Foundation to Message Queuing</span></span>

<span data-ttu-id="64635-103">In questo esempio viene illustrato il modo in cui un'applicazione Windows Communication Foundation (WCF) può inviare un messaggio a un'applicazione di Accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="64635-103">This sample demonstrates how a Windows Communication Foundation (WCF) application can send a message to a Message Queuing (MSMQ) application.</span></span> <span data-ttu-id="64635-104">Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="64635-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span> <span data-ttu-id="64635-105">Non è necessario che il servizio e il client siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="64635-105">The service and client do not have to be running at the same time.</span></span>

 <span data-ttu-id="64635-106">Il servizio riceve i messaggi dalla coda ed elabora gli ordini.</span><span class="sxs-lookup"><span data-stu-id="64635-106">The service receives messages from the queue and processes orders.</span></span> <span data-ttu-id="64635-107">Il servizio crea una coda transazionale e configura un gestore di messaggi basato sulla ricezione dei messaggi, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64635-107">The service creates a transactional queue and sets up a message received message handler, as shown in the following sample code.</span></span>

```csharp
static void Main(string[] args)
{
    if (!MessageQueue.Exists(
              ConfigurationManager.AppSettings["queueName"]))
       MessageQueue.Create(
           ConfigurationManager.AppSettings["queueName"], true);
        //Connect to the queue
        MessageQueue Queue = new
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);
    Queue.ReceiveCompleted +=
                 new ReceiveCompletedEventHandler(ProcessOrder);
    Queue.BeginReceive();
    Console.WriteLine("Order Service is running");
    Console.ReadLine();
}
```

 <span data-ttu-id="64635-108">Quando un messaggio viene ricevuto nella coda, viene chiamato il gestore dei messaggi `ProcessOrder`.</span><span class="sxs-lookup"><span data-stu-id="64635-108">When a message is received in the queue, the message handler `ProcessOrder` is invoked.</span></span>

```csharp
public static void ProcessOrder(Object source,
    ReceiveCompletedEventArgs asyncResult)
{
    try
    {
        // Connect to the queue.
        MessageQueue Queue = (MessageQueue)source;
        // End the asynchronous receive operation.
        System.Messaging.Message msg =
                     Queue.EndReceive(asyncResult.AsyncResult);
        msg.Formatter = new System.Messaging.XmlMessageFormatter(
                                new Type[] { typeof(PurchaseOrder) });
        PurchaseOrder po = (PurchaseOrder) msg.Body;
        Random statusIndexer = new Random();
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
        Console.WriteLine("Processing {0} ", po);
        Queue.BeginReceive();
    }
    catch (System.Exception ex)
    {
        Console.WriteLine(ex.Message);
    }

}
```

 <span data-ttu-id="64635-109">Il servizio estrae `ProcessOrder` dal corpo del messaggio di MSMQ ed elabora l'ordine.</span><span class="sxs-lookup"><span data-stu-id="64635-109">The service extracts the `ProcessOrder` from the MSMQ message body, and processes the order.</span></span>

 <span data-ttu-id="64635-110">Il nome della coda MSMQ viene specificato in una sezione appSettings del file di configurazione, come mostra la configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64635-110">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

> [!NOTE]
> <span data-ttu-id="64635-111">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="64635-111">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span>

 <span data-ttu-id="64635-112">Il client crea un ordine di acquisto e invia l'ordine di acquisto all'interno dell'ambito di una transazione, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64635-112">The client creates a purchase order and submits the purchase order within the scope of a transaction, as shown in the following sample code.</span></span>

```csharp
// Create the purchase order
PurchaseOrder po = new PurchaseOrder();
// Fill in the details
...

OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");

MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    client.SubmitPurchaseOrder(ordermsg);
    scope.Complete();
}
Console.WriteLine("Order has been submitted:{0}", po);

//Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

 <span data-ttu-id="64635-113">Il client utilizza un ordine client "in" personalizzato per inviare il messaggio MSMQ alla coda.</span><span class="sxs-lookup"><span data-stu-id="64635-113">The client uses a custom client in-order to send the MSMQ message to the queue.</span></span> <span data-ttu-id="64635-114">Poiché l'applicazione che riceve ed elabora il messaggio è un'applicazione MSMQ e non un'applicazione WCF, non esiste alcun contratto di servizio implicito tra le due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="64635-114">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="64635-115">Quindi, in questo scenario, non si può creare un proxy utilizzando lo strumento Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="64635-115">So, we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="64635-116">Il client personalizzato è essenzialmente lo stesso per tutte le applicazioni WCF che utilizzano l'associazione `MsmqIntegration` per inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="64635-116">The custom client is essentially the same for all WCF applications that use the `MsmqIntegration` binding to send messages.</span></span> <span data-ttu-id="64635-117">A differenza di altri client, non include varie operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="64635-117">Unlike other clients, it does not include a range of service operations.</span></span> <span data-ttu-id="64635-118">È un'operazione di solo invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="64635-118">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor
{
    public OrderProcessorClient(){}

    public OrderProcessorClient(string configurationName)
        : base(configurationName)
    { }

    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SubmitPurchaseOrder(msg);
    }
}
```

 <span data-ttu-id="64635-119">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="64635-119">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="64635-120">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="64635-120">You can see the service receive messages from the client.</span></span> <span data-ttu-id="64635-121">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="64635-121">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="64635-122">Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="64635-122">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="64635-123">Ad esempio è possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="64635-123">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

> [!NOTE]
> <span data-ttu-id="64635-124">Questo esempio richiede l'installazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="64635-124">This sample requires the installation of Message Queuing.</span></span> <span data-ttu-id="64635-125">Vedere le istruzioni di installazione in [Accodamento messaggi](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="64635-125">See the installation instructions in [Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)).</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="64635-126">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="64635-126">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="64635-127">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64635-127">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="64635-128">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="64635-128">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="64635-129">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="64635-129">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="64635-130">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="64635-130">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="64635-131">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="64635-131">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="64635-132">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="64635-132">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="64635-133">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="64635-133">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="64635-134">Fare clic con il pulsante destro del mouse su **code di messaggi private**, quindi scegliere **nuovo** > **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="64635-134">Right-click **Private Message Queues**, and then select **New** > **Private Queue**.</span></span>

    4. <span data-ttu-id="64635-135">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="64635-135">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="64635-136">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="64635-136">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="64635-137">Per compilare l' C# edizione o Visual Basic della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64635-137">To build the C# or Visual Basic edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="64635-138">Per eseguire l'esempio in una configurazione con un solo computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64635-138">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="64635-139">Eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="64635-139">Run the sample across computers</span></span>

1. <span data-ttu-id="64635-140">Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="64635-140">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="64635-141">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="64635-141">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="64635-142">Nel file Client.exe.config modificare l'indirizzo dell'endpoint del client e specificare il nome del computer del servizio anziché ".".</span><span class="sxs-lookup"><span data-stu-id="64635-142">In the Client.exe.config file, change the client endpoint address to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="64635-143">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="64635-143">On the service computer, launch Service.exe from a command prompt.</span></span>

5. <span data-ttu-id="64635-144">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="64635-144">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64635-145">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="64635-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="64635-146">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="64635-146">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="64635-147">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="64635-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64635-148">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="64635-148">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`

## <a name="see-also"></a><span data-ttu-id="64635-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64635-149">See also</span></span>

- [<span data-ttu-id="64635-150">Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="64635-150">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- <span data-ttu-id="64635-151">[Accodamento messaggi](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="64635-151">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
