---
title: Accodamento messaggi in Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
ms.openlocfilehash: 82e71afc911bff2504be15f7f9f2e736d943972b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584961"
---
# <a name="message-queuing-to-windows-communication-foundation"></a><span data-ttu-id="56ad7-102">Accodamento messaggi in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="56ad7-102">Message Queuing to Windows Communication Foundation</span></span>

<span data-ttu-id="56ad7-103">In questo esempio viene illustrato come un'applicazione di Accodamento messaggi (MSMQ) può inviare un messaggio MSMQ a un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="56ad7-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="56ad7-104">Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="56ad7-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="56ad7-105">Il contratto di servizio è `IOrderProcessor`che definisce un servizio unidirezionale adatto per l'uso con le code.</span><span class="sxs-lookup"><span data-stu-id="56ad7-105">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="56ad7-106">Un messaggio MSMQ non ha un'intestazione Action, pertanto non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi ai contratti dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="56ad7-106">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="56ad7-107">Pertanto, può essere presente un solo contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="56ad7-107">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="56ad7-108">Se si vuole definire più di un contratto dell'operazione per il servizio, l'applicazione deve fornire informazioni come quale intestazione nel messaggio MSMQ (ad esempio, l'etichetta o correlationID) può essere utilizzata per decidere quale contratto dell'operazione inviare.</span><span class="sxs-lookup"><span data-stu-id="56ad7-108">If you want to define more than one operation contract for the service, the application must provide information as to which header in the MSMQ message (for example, the label or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="56ad7-109">Il messaggio MSMQ non contiene informazioni come su quali intestazioni è stato eseguito il mapping ai diversi parametri del contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="56ad7-109">The MSMQ message does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="56ad7-110">Il parametro è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) che contiene il messaggio MSMQ sottostante.</span><span class="sxs-lookup"><span data-stu-id="56ad7-110">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), which contains the underlying MSMQ message.</span></span> <span data-ttu-id="56ad7-111">Il tipo "T" nella classe <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) rappresenta i dati serializzati nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="56ad7-111">The type "T" in the <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="56ad7-112">In questo esempio, il tipo `PurchaseOrder` è serializzato nel corpo del messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="56ad7-112">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

 <span data-ttu-id="56ad7-113">Nell'esempio di codice seguente viene mostrato il contratto di servizio del servizio di elaborazione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="56ad7-113">The following sample code shows the service contract of the order processing service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="56ad7-114">Il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-114">The service is self hosted.</span></span> <span data-ttu-id="56ad7-115">Quando si utilizza il trasporto MSMQ, la coda utilizzata deve essere creata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="56ad7-115">When using MSMQ, the queue used must be created in advance.</span></span> <span data-ttu-id="56ad7-116">Questa operazione può essere eseguita manualmente o mediante il codice.</span><span class="sxs-lookup"><span data-stu-id="56ad7-116">This can be done manually or through code.</span></span> <span data-ttu-id="56ad7-117">In questo esempio, il servizio verifica l'esistenza della coda e la crea se necessario.</span><span class="sxs-lookup"><span data-stu-id="56ad7-117">In this sample, the service checks for the existence of the queue and creates it if required.</span></span> <span data-ttu-id="56ad7-118">Il nome della coda viene letto dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="56ad7-118">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
    // Get the MSMQ queue name from the application settings in
    // configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];
    // Create the MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);
    …
}
```

 <span data-ttu-id="56ad7-119">Il servizio crea e apre una classe <xref:System.ServiceModel.ServiceHost> per `OrderProcessorService`, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-119">The service creates and opens a <xref:System.ServiceModel.ServiceHost> for the `OrderProcessorService`, as shown in the following sample code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
    serviceHost.Open();
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
    serviceHost.Close();
}
```

 <span data-ttu-id="56ad7-120">Il nome della coda MSMQ viene specificato in una sezione appSettings del file di configurazione, come mostra la configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-120">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="56ad7-121">Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="56ad7-121">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="56ad7-122">Nell'indirizzo dell'endpoint WCF viene specificato uno schema MSMQ. formatname e viene utilizzato localhost per il computer locale.</span><span class="sxs-lookup"><span data-stu-id="56ad7-122">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="56ad7-123">L'indirizzo della coda delle linee guida per l'indirizzamento del nome di formato MSMQ segue lo schema msmq.formatname.</span><span class="sxs-lookup"><span data-stu-id="56ad7-123">The address of the queue for each MSMQ Format Name addressing guidelines follows the msmq.formatname scheme.</span></span>

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="56ad7-124">L'applicazione client è un'applicazione MSMQ che utilizza il metodo <xref:System.Messaging.MessageQueue.Send%2A> per inviare un messaggio durevole e transazionale alla coda, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-124">The client application is an MSMQ application that uses the <xref:System.Messaging.MessageQueue.Send%2A> method to send a durable and transactional message to the queue, as shown in the following sample code.</span></span>

```csharp
//Connect to the queue.
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);

// Create the purchase order.
PurchaseOrder po = new PurchaseOrder();
po.CustomerId = "somecustomer.com";
po.PONumber = Guid.NewGuid().ToString();

PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
lineItem1.ProductId = "Blue Widget";
lineItem1.Quantity = 54;
lineItem1.UnitCost = 29.99F;

PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
lineItem2.ProductId = "Red Widget";
lineItem2.Quantity = 890;
lineItem2.UnitCost = 45.89F;

po.orderLineItems = new PurchaseOrderLineItem[2];
po.orderLineItems[0] = lineItem1;
po.orderLineItems[1] = lineItem2;

// Submit the purchase order.
Message msg = new Message();
msg.Body = po;
//Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{

    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
    // Complete the transaction.
    scope.Complete();

}
Console.WriteLine("Placed the order:{0}", po);
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="56ad7-125">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="56ad7-125">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="56ad7-126">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="56ad7-126">You can see the service receive messages from the client.</span></span> <span data-ttu-id="56ad7-127">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="56ad7-127">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="56ad7-128">Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-128">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="56ad7-129">Ad esempio è possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="56ad7-129">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="56ad7-130">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="56ad7-130">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="56ad7-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="56ad7-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="56ad7-132">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="56ad7-132">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="56ad7-133">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="56ad7-133">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="56ad7-134">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="56ad7-134">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="56ad7-135">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="56ad7-135">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="56ad7-136">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="56ad7-136">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="56ad7-137">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="56ad7-137">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="56ad7-138">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="56ad7-138">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="56ad7-139">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="56ad7-139">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="56ad7-140">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="56ad7-140">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="56ad7-141">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="56ad7-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="56ad7-142">Per eseguire l'esempio in una configurazione con un solo computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="56ad7-142">To run the sample in a single- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="56ad7-143">Eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="56ad7-143">Run the sample across computers</span></span>

1. <span data-ttu-id="56ad7-144">Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="56ad7-144">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="56ad7-145">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="56ad7-145">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="56ad7-146">Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".</span><span class="sxs-lookup"><span data-stu-id="56ad7-146">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="56ad7-147">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="56ad7-147">On the service computer, launch Service.exe from a command prompt.</span></span>

5. <span data-ttu-id="56ad7-148">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="56ad7-148">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56ad7-149">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="56ad7-149">The samples may already be installed on your computer.</span></span> <span data-ttu-id="56ad7-150">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="56ad7-150">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="56ad7-151">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="56ad7-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="56ad7-152">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="56ad7-152">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`

## <a name="see-also"></a><span data-ttu-id="56ad7-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56ad7-153">See also</span></span>

- [<span data-ttu-id="56ad7-154">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="56ad7-154">Queues in WCF</span></span>](../feature-details/queues-in-wcf.md)
- [<span data-ttu-id="56ad7-155">Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="56ad7-155">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- <span data-ttu-id="56ad7-156">[accodamento messaggi](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="56ad7-156">[Message Queuing](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))</span></span>
