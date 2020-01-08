---
title: Gestione dei messaggi non elaborabili in MSMQ 4,0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: 71ce6d3df69164aa0d565539bad5e843a7ed6a47
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337507"
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="f8ae3-102">Gestione dei messaggi non elaborabili in MSMQ 4,0</span><span class="sxs-lookup"><span data-stu-id="f8ae3-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="f8ae3-103">Questo esempio dimostra come eseguire la gestione dei messaggi non elaborabili in un servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="f8ae3-104">Questo esempio è basato sull'esempio di [associazione MSMQ transazionale](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="f8ae3-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="f8ae3-105">In questo esempio viene usato l'oggetto `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="f8ae3-106">Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

 <span data-ttu-id="f8ae3-107">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="f8ae3-108">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="f8ae3-109">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-109">The service receives messages from the queue.</span></span> <span data-ttu-id="f8ae3-110">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="f8ae3-111">Un messaggio non elaborabile è un messaggio che viene letto ripetutamente da una coda quando il servizio che legge il messaggio è in grado di elaborarlo e quindi termina la transazione nella quale viene letto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="f8ae3-112">In questi casi, il messaggio viene ritentato.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="f8ae3-113">Teoricamente l'operazione può ripetersi all'infinito se c'è un problema con il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="f8ae3-114">Notare che questo può accadere solo quando si usano transazioni per leggere dalla coda e richiamare il funzionamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-114">Note that this can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>

 <span data-ttu-id="f8ae3-115">In base alla versione di MSMQ, NetMsmqBinding supporta dal rilevamento limitato fino a quello completo dei messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="f8ae3-116">Dopo che il messaggio è stato rilevato come non elaborabile, è possibile gestirlo in alcuni modi.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="f8ae3-117">Di nuovo, in base alla versione di MSMQ, NetMsmqBinding supporta dalla gestione limitata fino a quella completa dei messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>

 <span data-ttu-id="f8ae3-118">In questo esempio vengono illustrate le funzionalità non elaborabili limitate fornite in Windows Server 2003 e la piattaforma [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e le funzionalità complete non elaborabili fornite in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-118">This sample illustrates the limited poison facilities provided on Windows Server 2003 and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] platform and the full poison facilities provided on Windows Vista.</span></span> <span data-ttu-id="f8ae3-119">In entrambi gli esempi, l'obiettivo è spostare il messaggio non elaborabile in un'altra coda che quindi può essere gestita da un servizio messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-119">In both samples, the objective is move the poison message out of the queue to another queue which then can be serviced by a poison message service.</span></span>

## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="f8ae3-120">Esempio di gestione dei messaggi non elaborabili di MSMQ v4.0</span><span class="sxs-lookup"><span data-stu-id="f8ae3-120">MSMQ v4.0 Poison Handling Sample</span></span>
 <span data-ttu-id="f8ae3-121">In Windows Vista, MSMQ fornisce una funzionalità di coda secondaria non elaborabile che può essere utilizzata per archiviare i messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-121">In Windows Vista, MSMQ provides a poison sub-queue facility that can be used to store poison messages.</span></span> <span data-ttu-id="f8ae3-122">In questo esempio viene illustrata la procedura consigliata per gestire i messaggi non elaborabili utilizzando Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-122">This sample demonstrates the best practice of dealing with poison messages using Windows Vista.</span></span>

 <span data-ttu-id="f8ae3-123">Il rilevamento dei messaggi non elaborabili in Windows Vista è piuttosto sofisticato.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-123">The poison message detection in Windows Vista is quite sophisticated.</span></span> <span data-ttu-id="f8ae3-124">Il rilevamento è agevolato da 3 proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-124">There are 3 properties that help with detection.</span></span> <span data-ttu-id="f8ae3-125"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> è il numero di volte che un determinato messaggio viene riletto dalla coda e inviato all'applicazione per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-125">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="f8ae3-126">Un messaggio viene riletto dalla coda quando è inserito di nuovo nella coda perché non può essere inviato all'applicazione o l'applicazione esegue il rollback della transazione nell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-126">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="f8ae3-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> è il numero di volte che il messaggio viene spostato nella coda di tentativi.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="f8ae3-128">Quando viene raggiunto <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>, il messaggio viene spostato nella coda di tentativi.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-128">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="f8ae3-129">La proprietà <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> è l'intervallo di tempo dopo il quale il messaggio viene spostato dalla coda di tentativi alla coda principale.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-129">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="f8ae3-130"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> viene reimpostato su 0.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-130">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="f8ae3-131">Viene eseguito un nuovo tentativo per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-131">The message is tried again.</span></span> <span data-ttu-id="f8ae3-132">Se tutti i tentativi di leggere il messaggio non sono riusciti, il messaggio è contrassegnato come non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-132">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>

 <span data-ttu-id="f8ae3-133">Una volta il messaggio è contrassegnato come non elaborabile, viene gestito in base alle impostazioni nell'enumerazione <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-133">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="f8ae3-134">Per reiterare i valori possibili:</span><span class="sxs-lookup"><span data-stu-id="f8ae3-134">To reiterate the possible values:</span></span>

- <span data-ttu-id="f8ae3-135">Fault (impostazione predefinita): per determinare l'errore del listener e anche dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-135">Fault (default): To fault the listener and also the service host.</span></span>

- <span data-ttu-id="f8ae3-136">Rilascia: per rilasciare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-136">Drop: To drop the message.</span></span>

- <span data-ttu-id="f8ae3-137">Move: per spostare il messaggio nella coda secondaria di messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-137">Move: To move the message to the poison message sub-queue.</span></span> <span data-ttu-id="f8ae3-138">Questo valore è disponibile solo in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-138">This value is available only on Windows Vista.</span></span>

- <span data-ttu-id="f8ae3-139">Reject: per rifiutare il messaggio, rispedendolo alla coda di messaggi non recapitabili del mittente.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-139">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="f8ae3-140">Questo valore è disponibile solo in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-140">This value is available only on Windows Vista.</span></span>

 <span data-ttu-id="f8ae3-141">Nell'esempio viene mostrato l'uso della disposizione `Move` per il messaggio non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-141">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="f8ae3-142">`Move` determina lo spostamento del messaggio nella coda secondaria non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-142">`Move` causes the message to move to the poison sub-queue.</span></span>

 <span data-ttu-id="f8ae3-143">Il contratto di servizio è `IOrderProcessor`che definisce un servizio unidirezionale adatto per l'uso con le code.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-143">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="f8ae3-144">L'operazione del servizio visualizza un messaggio indicante che l'ordine è in fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-144">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="f8ae3-145">Per dimostrare la funzionalità dei messaggi non elaborabili l'operazione del servizio `SubmitPurchaseOrder` genera un'eccezione per eseguire il rollback della transazione in una chiamata casuale del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-145">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to rollback the transaction on a random invocation of the service.</span></span> <span data-ttu-id="f8ae3-146">Questo fa in modo che il messaggio venga rimesso nella coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-146">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="f8ae3-147">Eventualmente il messaggio viene contrassegnato come non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-147">Eventually the message is marked as poison.</span></span> <span data-ttu-id="f8ae3-148">La configurazione è impostata per spostare il messaggio non elaborabile nella coda secondaria non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-148">The configuration is set to move the poison message to the poison sub-queue.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    static Random r = new Random(137);

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {

        int randomNumber = r.Next(10);

        if (randomNumber % 2 == 0)
        {
            Orders.Add(po);
            Console.WriteLine("Processing {0} ", po);
        }
        else
        {
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);
            Console.WriteLine();
            throw new Exception("Cannot process purchase order: " + po.PONumber);
        }
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted");
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Get MSMQ queue name from app settings in configuration.
        string queueName = ConfigurationManager.AppSettings["queueName"];

        // Create the transacted MSMQ queue if necessary.
        if (!System.Messaging.MessageQueue.Exists(queueName))
            System.Messaging.MessageQueue.Create(queueName, true);

        // Get the base address that is used to listen for WS-MetaDataExchange requests.
        // This is useful to generate a proxy for the client.
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        if(serviceHost.State != CommunicationState.Faulted) {
            serviceHost.Close();
        }

    }
}
```

 <span data-ttu-id="f8ae3-149">La configurazione del servizio comprende le seguenti proprietà dei messaggi non elaborabili: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` e `receiveErrorHandling` come è illustrato nel file di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-149">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>
  </appSettings>
  <system.serviceModel>
    <services>
      <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"
                  binding="netMsmqBinding"
                  bindingConfiguration="PoisonBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <bindings>
      <netMsmqBinding>
        <binding name="PoisonBinding"
                 receiveRetryCount="0"
                 maxRetryCycles="1"
                 retryCycleDelay="00:00:05"
                 receiveErrorHandling="Move">
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="f8ae3-150">Elaborazione dei messaggi dalla coda di messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="f8ae3-150">Processing messages from the poison message queue</span></span>
 <span data-ttu-id="f8ae3-151">Il servizio messaggi non elaborabili legge i messaggi dalla coda finale di messaggi non elaborabili e li elabora.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-151">The poison message service reads messages from the final poison message queue and processes them.</span></span>

 <span data-ttu-id="f8ae3-152">I messaggi nella coda di messaggi non elaborabili sono indirizzati al servizio che sta elaborando il messaggio, il quale può essere diverso dall'endpoint del servizio messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-152">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="f8ae3-153">Pertanto, quando il servizio messaggi non elaborabili legge messaggi dalla coda, il livello del canale WCF trova la mancata corrispondenza negli endpoint e non invia il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-153">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="f8ae3-154">In questo caso, il messaggio è indirizzato al servizio di elaborazione ordini ma viene ricevuto dal servizio messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-154">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="f8ae3-155">Per continuare a ricevere il messaggio anche se è indirizzato a un endpoint diverso, è necessario aggiungere un `ServiceBehavior` per filtrare gli indirizzi nei quali il criterio di corrispondenza è qualsiasi endpoint del servizio al quale il messaggio è indirizzato.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-155">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="f8ae3-156">Questo è necessario per elaborare correttamente i messaggi che vengono letti dalla coda di messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-156">This is required to successfully process messages that you read from the poison message queue.</span></span>

 <span data-ttu-id="f8ae3-157">L'implementazione stessa del servizio messaggi non elaborabili è molto simile all'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-157">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="f8ae3-158">Implementa il contratto ed elabora gli ordini.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-158">It implements the contract and processes the orders.</span></span> <span data-ttu-id="f8ae3-159">Di seguito è riportato l'esempio di codice completo:</span><span class="sxs-lookup"><span data-stu-id="f8ae3-159">The code example is as follows.</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted...exiting app");
        Environment.Exit(1);
    }

    // Host the service within this EXE console application.
    public static void Main()
    {

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The poison message service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHostBase to shutdown the service.
        if(serviceHost.State != CommunicationState.Faulted)
        {
            serviceHost.Close();
        }
    }
```

 <span data-ttu-id="f8ae3-160">Diversamente dal servizio di elaborazione ordini che legge i messaggi dalla coda degli ordini, il servizio messaggi non elaborabili legge i messaggi dalla coda secondaria non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-160">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison sub-queue.</span></span> <span data-ttu-id="f8ae3-161">La coda non elaborabile è una coda secondaria della coda principale, denominata "non elaborabile" ed è generata automaticamente da MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-161">The poison queue is a sub-queue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="f8ae3-162">Per accedervi, fornire il nome della coda principale seguito da un "," e il nome della coda secondaria, in questo caso -"poison", come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-162">To access it, provide the main queue name followed by a ";" and the sub-queue name, in this case -"poison", as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="f8ae3-163">Nell'esempio per MSMQ v3.0, il nome della coda non elaborabile non è una coda secondaria, ma la coda nella quale viene spostato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-163">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >
        </endpoint>
      </service>
    </services>

  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="f8ae3-164">Quando si esegue l'esempio, le attività del client, del servizio e del servizio messaggi non elaborabili vengono visualizzate nelle finestre della console.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-164">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="f8ae3-165">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-165">You can see the service receive messages from the client.</span></span> <span data-ttu-id="f8ae3-166">Premere INVIO in ciascuna finestra della console per arrestare i servizi.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-166">Press ENTER in each console window to shut down the services.</span></span>

 <span data-ttu-id="f8ae3-167">Il servizio avvia l'esecuzione, elaborando gli ordini e in modo casuale inizia a terminare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-167">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="f8ae3-168">Se il messaggio indica che ha elaborato l'ordine, è possibile eseguire di nuovo il client per inviare un altro messaggio finché non si nota che il servizio ha effettivamente terminato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-168">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="f8ae3-169">In base alle impostazioni dei messaggi non elaborabili configurate, l'elaborazione del messaggio viene tentata una volta prima che questo venga rimosso dalla coda finale non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-169">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
```

 <span data-ttu-id="f8ae3-170">Avviare il servizio messaggi non elaborabili per leggere il messaggio non elaborabile dalla coda non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-170">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="f8ae3-171">In questo esempio, il servizio messaggi non elaborabili legge il messaggio e lo elabora.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-171">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="f8ae3-172">È possibile osservare che l'ordine di acquisto terminato e impostato come non elaborabile viene letto dal servizio messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-172">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8ae3-173">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f8ae3-173">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f8ae3-174">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8ae3-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f8ae3-175">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-175">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="f8ae3-176">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-176">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="f8ae3-177">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-177">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="f8ae3-178">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-178">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="f8ae3-179">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-179">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="f8ae3-180">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="f8ae3-180">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="f8ae3-181">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-181">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="f8ae3-182">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="f8ae3-182">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="f8ae3-183">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-183">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="f8ae3-184">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8ae3-184">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="f8ae3-185">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, modificare i nomi delle code in modo da riflettere il nome host effettivo anziché localhost e seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8ae3-185">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

 <span data-ttu-id="f8ae3-186">Per impostazione predefinita con il trasporto dell'associazione `netMsmqBinding` è abilitata la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-186">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="f8ae3-187">Il tipo di sicurezza del trasporto è determinato da due proprietà, `MsmqAuthenticationMode` e `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-187">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="f8ae3-188">Per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-188">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="f8ae3-189">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, deve appartenere a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-189">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="f8ae3-190">Se si esegue questo esempio in un computer che non appartiene a un dominio, si riceve l'errore seguente: "Il certificato interno del servizio di accodamento messaggi non esiste".</span><span class="sxs-lookup"><span data-stu-id="f8ae3-190">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="f8ae3-191">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8ae3-191">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="f8ae3-192">Se il computer non appartiene a un dominio, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e livello di protezione su `None` come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f8ae3-192">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="f8ae3-193">Verificare che l'endpoint sia associato al binding impostando l'attributo bindingConfiguration dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-193">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>

2. <span data-ttu-id="f8ae3-194">Assicurarsi di modificare la configurazione in PoisonMessageServer, sul server e sul client prima che di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-194">Ensure that you change the configuration on the PoisonMessageServer, server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8ae3-195">L'impostazione di `security mode` su `None` è equivalente all'impostazione di `MsmqAuthenticationMode`, `MsmqProtectionLevel` e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-195">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3. <span data-ttu-id="f8ae3-196">Affinché Metadata Exchange funzioni, registriamo un URL con associazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-196">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="f8ae3-197">Ciò richiede che il servizio venga eseguito in una finestra di comando elevata.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-197">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="f8ae3-198">In caso contrario, si otterrà un'eccezione, ad esempio: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-198">Otherwise, you get an exception such as: `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f8ae3-199">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f8ae3-200">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-200">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="f8ae3-201">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8ae3-202">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f8ae3-202">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
