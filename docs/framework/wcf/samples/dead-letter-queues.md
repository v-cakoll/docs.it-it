---
title: Code di messaggi non recapitabili
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: 244920eb9a0cdb33f4d5d83b939fe1166f4f5fcd
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837909"
---
# <a name="dead-letter-queues"></a><span data-ttu-id="59352-102">Code di messaggi non recapitabili</span><span class="sxs-lookup"><span data-stu-id="59352-102">Dead Letter Queues</span></span>
<span data-ttu-id="59352-103">Questo esempio dimostra come gestire ed elaborare messaggi il cui recapito non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="59352-103">This sample demonstrates how to handle and process messages that have failed delivery.</span></span> <span data-ttu-id="59352-104">Si basa sull'esempio di [associazione MSMQ transazionale](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="59352-104">It is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="59352-105">In questo esempio viene usata l'associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="59352-105">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="59352-106">Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="59352-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>

> [!NOTE]
> <span data-ttu-id="59352-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="59352-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="59352-108">In questo esempio viene illustrata ogni coda di messaggi non recapitabili dell'applicazione disponibile solo in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="59352-108">This sample demonstrates each application dead letter queue that is only available on Windows Vista.</span></span> <span data-ttu-id="59352-109">L'esempio può essere modificato per usare le code a livello di sistema predefinite per MSMQ 3.0 su [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59352-109">The sample can be modified to use the default system-wide queues for MSMQ 3.0 on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>

 <span data-ttu-id="59352-110">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="59352-110">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="59352-111">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="59352-111">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="59352-112">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="59352-112">The service receives messages from the queue.</span></span> <span data-ttu-id="59352-113">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="59352-113">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>

 <span data-ttu-id="59352-114">Poiché la comunicazione in coda può comportare una certa quantità di inattività, è possibile associare un valore di durata al messaggio per garantire che non venga recapitato all'applicazione se è stato superato il periodo.</span><span class="sxs-lookup"><span data-stu-id="59352-114">Because queued communication can involve a certain amount of dormancy, you may want to associate a time-to-live value on the message to ensure that the message does not get delivered to the application if it has gone past the time.</span></span> <span data-ttu-id="59352-115">Vi sono anche casi nei quali un'applicazione deve essere informata del mancato recapito di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-115">There are also cases, where an application must be informed whether a message failed delivery.</span></span> <span data-ttu-id="59352-116">In tutti di questi casi, quali la scadenza della durata del messaggio o il mancato recapito, il messaggio viene inserito in una coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-116">In all of these cases, such as when the time-to-live on the message has expired or the message failed delivery, the message is put in a dead letter queue.</span></span> <span data-ttu-id="59352-117">L'applicazione di invio può leggere quindi i messaggi nella coda di messaggi non recapitabili e adottare azioni correttive che vanno da nessuna azione alla correzione delle ragioni del mancato recapito e reinvio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-117">The sending application can then read the messages in the dead-letter queue and take corrective actions that range from no action to correcting the reasons for failed delivery and resending the message.</span></span>

 <span data-ttu-id="59352-118">La coda di messaggi non recapitabili nell'associazione `NetMsmqBinding` è espressa nelle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="59352-118">The dead-letter queue in the `NetMsmqBinding` binding is expressed in the following properties:</span></span>

- <span data-ttu-id="59352-119">Proprietà <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> per esprimere il tipo di coda di messaggi non recapitabili richiesta dal client.</span><span class="sxs-lookup"><span data-stu-id="59352-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> property to express the kind of dead-letter queue required by the client.</span></span> <span data-ttu-id="59352-120">L'enumerazione contiene i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="59352-120">This enumeration has the following values:</span></span>

- <span data-ttu-id="59352-121">`None`: non viene richiesta alcuna coda di messaggi non recapitabili dal client.</span><span class="sxs-lookup"><span data-stu-id="59352-121">`None`: No dead-letter queue is required by the client.</span></span>

- <span data-ttu-id="59352-122">`System`: viene usata la coda di messaggi non recapitabili di sistema per archiviare i messaggi non recapitati.</span><span class="sxs-lookup"><span data-stu-id="59352-122">`System`: The system dead-letter queue is used to store dead messages.</span></span> <span data-ttu-id="59352-123">La coda di messaggi non recapitabili di sistema è condivisa da tutte le applicazioni in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="59352-123">The system dead-letter queue is shared by all applications running on the computer.</span></span>

- <span data-ttu-id="59352-124">`Custom`: per archiviare i messaggi non recapitati viene usata una coda di messaggi non recapitabili personalizzata specificata usando la proprietà <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>.</span><span class="sxs-lookup"><span data-stu-id="59352-124">`Custom`: A custom dead-letter queue specified using the <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property is used to store dead messages.</span></span> <span data-ttu-id="59352-125">Questa funzionalità è disponibile solo in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="59352-125">This feature is only available on Windows Vista.</span></span> <span data-ttu-id="59352-126">Viene usata quando l'applicazione deve usare la propria coda di messaggi non recapitabili invece di condividerla con altre applicazioni in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="59352-126">This is used when the application must use its own dead letter queue instead of sharing it with other applications running on the same computer.</span></span>

- <span data-ttu-id="59352-127">Proprietà <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> per esprimere la coda specifica da usare come coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property to express the specific queue to use as a dead-letter queue.</span></span> <span data-ttu-id="59352-128">Questa operazione è disponibile solo in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="59352-128">This is available only in Windows Vista.</span></span>

 <span data-ttu-id="59352-129">In questo esempio, il client invia un gruppo di messaggi al servizio dall'interno dell'ambito di una transazione e specifica un valore arbitrariamente basso per la "durata" di questi messaggi (circa 2 secondi).</span><span class="sxs-lookup"><span data-stu-id="59352-129">In this sample, the client sends a batch of messages to the service from within the scope of a transaction and specifies an arbitrarily low value for "time-to-live" for these messages (about 2 seconds).</span></span> <span data-ttu-id="59352-130">Il client specifica anche una coda di messaggi non recapitabili personalizzata da usare per accodare i messaggi che sono scaduti.</span><span class="sxs-lookup"><span data-stu-id="59352-130">The client also specifies a custom dead-letter queue to use to enqueue the messages that have expired.</span></span>

 <span data-ttu-id="59352-131">L'applicazione client può leggere i messaggi nella coda di messaggi non recapitabili e ritentare l'invio del messaggio o correggere l'errore che ha causato l'inserimento del messaggio originale nella coda dei messaggi non recapitabili e inviare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-131">The client application can read the messages in the dead-letter queue and either retry sending the message or correct the error that caused the original message to be placed in the dead-letter queue and send the message.</span></span> <span data-ttu-id="59352-132">Nell'esempio, il client visualizza un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="59352-132">In the sample, the client displays an error message.</span></span>

 <span data-ttu-id="59352-133">Il contratto del servizio è `IOrderProcessor`, come mostrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="59352-133">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="59352-134">Il codice del servizio nell'esempio è quello dell' [associazione MSMQ transazionale](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="59352-134">The service code in the sample is that of the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>

 <span data-ttu-id="59352-135">La comunicazione con il servizio avviene all'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="59352-135">Communication with the service takes place within the scope of a transaction.</span></span> <span data-ttu-id="59352-136">Il servizio legge messaggi dalla coda, esegue l'operazione e quindi visualizza i risultati dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59352-136">The service reads messages from the queue, performs the operation and then displays the results of the operation.</span></span> <span data-ttu-id="59352-137">L'applicazione crea anche una coda per i messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-137">The application also creates a dead-letter queue for dead-letter messages.</span></span>

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
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

        //Create a transaction scope.
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 <span data-ttu-id="59352-138">La configurazione del client specifica una durata breve per il raggiungimento del servizio da parte del messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-138">The client's configuration specifies a short duration for the message to reach the service.</span></span> <span data-ttu-id="59352-139">Se il messaggio non può essere trasmesso entro la durata specificata, scade e viene spostato nella coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-139">If the message cannot be transmitted within the duration specified, the message expires and is moved to the dead-letter queue.</span></span>

> [!NOTE]
> <span data-ttu-id="59352-140">Per il client è possibile recapitare il messaggio alla coda del servizio entro il periodo specificato.</span><span class="sxs-lookup"><span data-stu-id="59352-140">It is possible for the client to deliver the message to the service queue within the specified time.</span></span> <span data-ttu-id="59352-141">Per garantire di vedere il servizio dei messaggi non recapitabili in azione, è necessario eseguire il client prima di avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="59352-141">To ensure you see the dead-letter service in action, you should run the client before starting the service.</span></span> <span data-ttu-id="59352-142">Il messaggio scade e viene recapitato al servizio messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-142">The message times out and is delivered to the dead-letter service.</span></span>

 <span data-ttu-id="59352-143">L'applicazione deve definire quale coda usare per i messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-143">The application must define which queue to use as its dead-letter queue.</span></span> <span data-ttu-id="59352-144">Se non viene specificata alcuna coda, per accodare i messaggi non recapitabili viene usata la coda di messaggi non recapitabili relativi a transazioni a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="59352-144">If no queue is specified, the default system-wide transactional dead-letter queue is used to queue dead messages.</span></span> <span data-ttu-id="59352-145">In questo esempio, l'applicazione client specifica la propria coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-145">In this example, the client application specifies its own application dead-letter queue.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 <span data-ttu-id="59352-146">Il servizio di messaggi non recapitabili legge i messaggi dalla coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-146">The dead-letter message service reads messages from the dead-letter queue.</span></span> <span data-ttu-id="59352-147">Il servizio messaggi non recapitabili implementa il contratto `IOrderProcessor`.</span><span class="sxs-lookup"><span data-stu-id="59352-147">The dead-letter message service implements the `IOrderProcessor` contract.</span></span> <span data-ttu-id="59352-148">La relativa implementazione tuttavia non ha lo scopo di elaborare ordini.</span><span class="sxs-lookup"><span data-stu-id="59352-148">Its implementation however is not to process orders.</span></span> <span data-ttu-id="59352-149">Il servizio messaggi non recapitabili è un servizio client e non ha funzionalità per elaborare ordini.</span><span class="sxs-lookup"><span data-stu-id="59352-149">The dead-letter message service is a client service and does not have the facility to process orders.</span></span>

> [!NOTE]
> <span data-ttu-id="59352-150">La coda di messaggi non recapitabili è una coda client ed è locale per il gestore delle code client.</span><span class="sxs-lookup"><span data-stu-id="59352-150">The dead-letter queue is a client queue and is local to the client queue manager.</span></span>

 <span data-ttu-id="59352-151">L'implementazione del servizio messaggi non recapitabili verifica la ragione del mancato recapito di un messaggio e adotta misure correttive.</span><span class="sxs-lookup"><span data-stu-id="59352-151">The dead-letter message service implementation checks for the reason a message failed delivery and takes corrective measures.</span></span> <span data-ttu-id="59352-152">La ragione di un errore di messaggio viene acquisita in due enumerazioni, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> e <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span><span class="sxs-lookup"><span data-stu-id="59352-152">The reason for a message failure is captured in two enumerations, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> and <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span></span> <span data-ttu-id="59352-153">È possibile recuperare la <xref:System.ServiceModel.Channels.MsmqMessageProperty> dal <xref:System.ServiceModel.OperationContext> come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="59352-153">You can retrieve the <xref:System.ServiceModel.Channels.MsmqMessageProperty> from the <xref:System.ServiceModel.OperationContext> as shown in the following sample code:</span></span>

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 <span data-ttu-id="59352-154">I messaggi nella coda di messaggi non recapitabili sono indirizzati al servizio che sta elaborando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-154">Messages in the dead-letter queue are messages that are addressed to the service that is processing the message.</span></span> <span data-ttu-id="59352-155">Pertanto, quando il servizio messaggi non recapitabili legge messaggi dalla coda, il livello del canale Windows Communication Foundation (WCF) trova la mancata corrispondenza negli endpoint e non invia il messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-155">Therefore, when the dead-letter message service reads messages from the queue, the Windows Communication Foundation (WCF) channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="59352-156">In questo caso, il messaggio è indirizzato al servizio di elaborazione ordini ma viene ricevuto dal servizio messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-156">In this case, the message is addressed to the order processing service but is received by the dead-letter message service.</span></span> <span data-ttu-id="59352-157">Per ricevere un messaggio indirizzato a un altro endpoint, in `ServiceBehavior` viene specificato un filtro degli indirizzi con il quale confrontare qualsiasi indirizzo.</span><span class="sxs-lookup"><span data-stu-id="59352-157">To receive a message that is addressed to a different endpoint, an address filter to match any address is specified in the `ServiceBehavior`.</span></span> <span data-ttu-id="59352-158">Questo è necessario per elaborare correttamente i messaggi che vengono letti dalla coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="59352-158">This is required to successfully process messages that are read from the dead-letter queue.</span></span>

 <span data-ttu-id="59352-159">In questo esempio, il servizio messaggi non recapitabili invia nuovamente il messaggio se il motivo dell'errore è che si è verificato il timeout del messaggio. Per tutti gli altri motivi, viene visualizzato l'errore di recapito, come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="59352-159">In this sample, the dead-letter message service resends the message if the reason for failure is that the message timed out. For all other reasons, it displays the delivery failure, as shown in the following sample code:</span></span>

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 <span data-ttu-id="59352-160">Nell'esempio seguente viene illustrata la configurazione per un messaggio non recapitabile.</span><span class="sxs-lookup"><span data-stu-id="59352-160">The following sample shows the configuration for a dead-letter message:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="59352-161">Nell'esempio, per visualizzare il funzionamento della coda di messaggi non recapitabili per ciascuna applicazione è necessario eseguire 3 file eseguibili: il client, il servizio e un servizio messaggi non recapitabili che legge dalla coda di messaggi non recapitabili di ciascuna applicazione e reinvia il messaggio al servizio.</span><span class="sxs-lookup"><span data-stu-id="59352-161">In running the sample, there are 3 executables to run to see how the dead-letter queue works for each application; the client, service and a dead-letter service that reads from the dead-letter queue for each application and resends the message to the service.</span></span> <span data-ttu-id="59352-162">Tutte sono applicazioni console con output in finestre di console.</span><span class="sxs-lookup"><span data-stu-id="59352-162">All are console applications with output in console windows.</span></span>

> [!NOTE]
> <span data-ttu-id="59352-163">Poiché viene usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="59352-163">Because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="59352-164">È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="59352-164">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="59352-165">È necessario avviare il servizio e arrestarlo per consentire la creazione della coda.</span><span class="sxs-lookup"><span data-stu-id="59352-165">You should start the service and shut it down so that the queue can be created.</span></span>

 <span data-ttu-id="59352-166">Quando viene seguito, il client visualizza il messaggio.</span><span class="sxs-lookup"><span data-stu-id="59352-166">When running the client, the client displays the message:</span></span>

```console
Press <ENTER> to terminate client.
```

 <span data-ttu-id="59352-167">Il client ha tentato di inviare il messaggio ma con un breve timeout, il messaggio è scaduto e ora si trova nella coda di messaggi non recapitabili di ciascuna applicazione.</span><span class="sxs-lookup"><span data-stu-id="59352-167">The client attempted to send the message but with a short timeout, the message expired and is now queued in the dead-letter queue for each application.</span></span>

 <span data-ttu-id="59352-168">Viene quindi eseguito il servizio messaggi non recapitabili che legge il messaggio, visualizza il codice di errore e reinvia il messaggio al servizio.</span><span class="sxs-lookup"><span data-stu-id="59352-168">You then run the dead-letter service, which reads the message and displays the error code and resends the message back to the service.</span></span>

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 <span data-ttu-id="59352-169">Il servizio viene avviato e quindi legge il messaggio reinviato e lo elabora.</span><span class="sxs-lookup"><span data-stu-id="59352-169">The service starts and then reads the resent message and processes it.</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="59352-170">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="59352-170">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="59352-171">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59352-171">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="59352-172">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="59352-172">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="59352-173">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="59352-173">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="59352-174">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="59352-174">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="59352-175">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="59352-175">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="59352-176">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="59352-176">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="59352-177">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="59352-177">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="59352-178">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="59352-178">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="59352-179">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="59352-179">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="59352-180">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="59352-180">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="59352-181">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59352-181">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="59352-182">Per eseguire l'esempio in una configurazione singola o tra più computer, modificare i nomi della coda in modo appropriato, sostituendo localhost con il nome completo del computer e seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59352-182">To run the sample in a single- or cross-computer configuration change queue names appropriately, replacing localhost with full name of the computer and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="59352-183">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="59352-183">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="59352-184">Se il computer non appartiene a un dominio, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e livello di protezione su `None` come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="59352-184">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     <span data-ttu-id="59352-185">Verificare che l'endpoint sia associato all'associazione impostando l'attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="59352-185">Ensure the endpoint is associated with the binding by setting the endpoint's `bindingConfiguration` attribute.</span></span>

2. <span data-ttu-id="59352-186">Assicurarsi di modificare la configurazione in DeadLetterService, sul server e sul client prima che di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="59352-186">Ensure that you change the configuration on the DeadLetterService, server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59352-187">L'impostazione di `security mode` su `None` è equivalente all'impostazione di `MsmqAuthenticationMode`, `MsmqProtectionLevel` e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="59352-187">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

## <a name="comments"></a><span data-ttu-id="59352-188">Comments</span><span class="sxs-lookup"><span data-stu-id="59352-188">Comments</span></span>
 <span data-ttu-id="59352-189">Per impostazione predefinita con il trasporto dell'associazione `netMsmqBinding` è abilitata la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="59352-189">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="59352-190">Il tipo di sicurezza del trasporto è determinato da due proprietà, `MsmqAuthenticationMode` e `MsmqProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="59352-190">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="59352-191">Per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`.</span><span class="sxs-lookup"><span data-stu-id="59352-191">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="59352-192">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, deve appartenere a un dominio.</span><span class="sxs-lookup"><span data-stu-id="59352-192">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="59352-193">Se si esegue questo esempio in un computer che non appartiene a un dominio, si riceve l'errore seguente: "Il certificato interno del servizio di accodamento messaggi non esiste".</span><span class="sxs-lookup"><span data-stu-id="59352-193">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59352-194">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="59352-194">The samples may already be installed on your computer.</span></span> <span data-ttu-id="59352-195">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="59352-195">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="59352-196">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="59352-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59352-197">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="59352-197">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
