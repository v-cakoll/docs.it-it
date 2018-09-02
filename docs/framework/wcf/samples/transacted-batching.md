---
title: Batch transazionale.
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: abada9aaf5fac8f05599467f385e708e1898832f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416648"
---
# <a name="transacted-batching"></a><span data-ttu-id="3994f-102">Batch transazionale.</span><span class="sxs-lookup"><span data-stu-id="3994f-102">Transacted Batching</span></span>
<span data-ttu-id="3994f-103">Questo esempio dimostra come raggruppare letture transazionali usando Accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="3994f-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="3994f-104">Il batch transazionale è una funzionalità di ottimizzazione delle prestazioni per le letture transazionali nella comunicazione in coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3994f-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3994f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3994f-106">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="3994f-107">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="3994f-108">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-108">The service receives messages from the queue.</span></span> <span data-ttu-id="3994f-109">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3994f-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="3994f-110">Nell'esempio viene dimostrato il batch transazionale.</span><span class="sxs-lookup"><span data-stu-id="3994f-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="3994f-111">Il batch transazionale è un comportamento che consente di usare una singola transazione per la lettura di molti messaggi nella coda e la relativa elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3994f-112">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3994f-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3994f-113">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3994f-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3994f-114">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="3994f-115">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="3994f-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="3994f-116">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3994f-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="3994f-117">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="3994f-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="3994f-118">Aprire Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3994f-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="3994f-119">Espandere la **funzionalità** scheda.</span><span class="sxs-lookup"><span data-stu-id="3994f-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="3994f-120">Fare doppio clic su **code Private**e selezionare **New**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="3994f-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="3994f-121">Verificare i **transazionale** casella.</span><span class="sxs-lookup"><span data-stu-id="3994f-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="3994f-122">Immettere `ServiceModelSamplesTransacted` come il nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3994f-123">In questo esempio il client invia centinaia di messaggi come parte del batch.</span><span class="sxs-lookup"><span data-stu-id="3994f-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="3994f-124">È pertanto normale che l'applicazione di servizio impieghi del tempo per elaborarli.</span><span class="sxs-lookup"><span data-stu-id="3994f-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="3994f-125">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3994f-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="3994f-126">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3994f-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="3994f-127">Per eseguire l'esempio in un computer appartenente a un gruppo di lavoro o privo di integrazione con Active Directory</span><span class="sxs-lookup"><span data-stu-id="3994f-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="3994f-128">Per impostazione predefinita con l'associazione <xref:System.ServiceModel.NetMsmqBinding>, la sicurezza del trasporto è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3994f-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="3994f-129">Sono disponibili due proprietà pertinenti per la sicurezza del trasporto MSMQ <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> e <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` per impostazione predefinita, la modalità di autenticazione è impostata su `Windows` e il livello di protezione è impostato su `Sign`.</span><span class="sxs-lookup"><span data-stu-id="3994f-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="3994f-130">Affinché MSMQ fornisca la funzionalità di autenticazione e firma, è necessario che faccia parte di un dominio e che sia installata l'opzione di integrazione di Active Directory per MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3994f-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="3994f-131">Se si esegue questo esempio in un computer che non soddisfà questi criteri si riceve un errore.</span><span class="sxs-lookup"><span data-stu-id="3994f-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="3994f-132">Se il computer non appartiene a un dominio o non è installato con l'integrazione di Active Directory, disattivare la sicurezza del trasporto impostando la modalità di autenticazione e il livello di protezione su `None` come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3994f-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="3994f-133">Assicurarsi di modificare la configurazione sul server e sul client prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3994f-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3994f-134">L'impostazione di `security``mode` su `None` è equivalente all'impostazione di <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> e della sicurezza `Message` su `None`.</span><span class="sxs-lookup"><span data-stu-id="3994f-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="3994f-135">Per eseguire il database in un computer remoto, modificare la stringa di connessione per puntare al computer sul quale risiede il database.</span><span class="sxs-lookup"><span data-stu-id="3994f-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3994f-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3994f-136">Requirements</span></span>  
 <span data-ttu-id="3994f-137">Per eseguire questo esempio, è necessario che MSMQ sia installato ed è necessario SQL o SQL ExpressSQL.</span><span class="sxs-lookup"><span data-stu-id="3994f-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3994f-138">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="3994f-138">Demonstrates</span></span>  
 <span data-ttu-id="3994f-139">Questo esempio dimostra il comportamento batch transazionale.</span><span class="sxs-lookup"><span data-stu-id="3994f-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="3994f-140">Il batch transazionale è una funzionalità di ottimizzazione delle prestazione fornita con il trasporto in coda MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3994f-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="3994f-141">Quando vengono usate transazioni per inviare e ricevere messaggi, di fatto vi sono 2 transazioni distinte.</span><span class="sxs-lookup"><span data-stu-id="3994f-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="3994f-142">Quando il client invia messaggi all'interno dell'ambito di una transazione, questa è locale per il client e il gestore delle code client.</span><span class="sxs-lookup"><span data-stu-id="3994f-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="3994f-143">Quando il servizio riceve messaggi all'interno dell'ambito di una transazione, questa è locale per il servizio e il gestore delle code di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="3994f-144">È molto importante ricordare che il client e il servizio non partecipano alla stessa transazione; essi usano invece transazioni diverse per le operazioni con la coda, quali l'invio e la ricezione.</span><span class="sxs-lookup"><span data-stu-id="3994f-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="3994f-145">Nell'esempio viene usata una sola transazione per l'esecuzione di più operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="3994f-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="3994f-146">Questa viene usata solo come funzionalità di ottimizzazione delle prestazioni e non influisce sulla semantica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="3994f-147">L'esempio è basato sul [transazionale associazione MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="3994f-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3994f-148">Commenti</span><span class="sxs-lookup"><span data-stu-id="3994f-148">Comments</span></span>  
 <span data-ttu-id="3994f-149">In questo esempio, il client invia un batch di messaggi al servizio dall'interno dell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="3994f-150">Per mostrare l'ottimizzazione delle prestazioni viene inviato un numero elevato di messaggi; in questo caso, fino a 2500 messaggi.</span><span class="sxs-lookup"><span data-stu-id="3994f-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="3994f-151">I messaggi inviati alla coda vengono quindi ricevuti dal servizio fra l'ambito della transazione definito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3994f-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="3994f-152">Senza il raggruppamento, ciò si traduce in 2500 transazioni per ogni chiamata dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3994f-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="3994f-153">Questo influisce sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="3994f-153">This impacts performance of the system.</span></span> <span data-ttu-id="3994f-154">Poiché sono coinvolti due gestori due gestori di risorse, la coda MSMQ e il database `Orders`, ciascuna di queste transazioni è una transazione DTC.</span><span class="sxs-lookup"><span data-stu-id="3994f-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="3994f-155">Ciò viene ottimizzato usando un numero molto inferiore di transazioni per garantire che a un batch di messaggi e chiamate delle operazioni del servizio abbia luogo in un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="3994f-156">La funzionalità batch viene usata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3994f-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="3994f-157">Specificando il comportamento del batch transazionale nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="3994f-158">Specificando una dimensione di batch in termini di numero di messaggi da leggere in un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="3994f-159">Specificando il numero massimo di batch simultanei da eseguire.</span><span class="sxs-lookup"><span data-stu-id="3994f-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="3994f-160">In questo esempio, vengono dimostrati i guadagni di prestazioni tramite la riduzione del numero di transazioni assicurando che vengano chiamate 100 operazioni del servizio in una sola transazione prima di eseguire il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="3994f-161">Il comportamento del servizio definisce un comportamento dell'operazione con `TransactionScopeRequired` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="3994f-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="3994f-162">Questo assicura che lo stesso ambito della transazione che viene usato per recuperare il messaggio dalla coda sia usato da tutti i gestori di risorse ai quali accede il metodo.</span><span class="sxs-lookup"><span data-stu-id="3994f-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="3994f-163">In questo esempio, viene usato un database di base per archiviare le informazioni sull'ordine di acquisto contenute nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="3994f-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="3994f-164">L'ambito della transazione garantisce anche che se il metodo genera un'eccezione, il messaggio viene restituito alla coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="3994f-165">Senza impostare questo comportamento dell'operazione, un canale in coda crea una transazione per leggere il messaggio dalla coda e ne esegue automaticamente il commit prima che venga inviato in modo che se l'operazione non riesce, il messaggio va perduto.</span><span class="sxs-lookup"><span data-stu-id="3994f-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="3994f-166">Lo scenario più comune per le operazioni del servizio è di inserirsi nella transazione che viene usata per leggere il messaggio dalla coda come dimostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3994f-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="3994f-167">Notare che `ReleaseServiceInstanceOnTransactionComplete` è impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="3994f-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="3994f-168">Si tratta di un requisito importante per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="3994f-168">This is an important requirement for batching.</span></span> <span data-ttu-id="3994f-169">La proprietà `ReleaseServiceInstanceOnTransactionComplete` in `ServiceBehaviorAttribute` indica che cosa fare con l'istanza del servizio dopo che la transazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="3994f-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="3994f-170">Per impostazione predefinita, l'istanza del servizio viene rilasciata al completa della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="3994f-171">L'aspetto centrale del raggruppamento è l'uso di una singola transazione per la lettura e l'invio di molti messaggi nella coda.</span><span class="sxs-lookup"><span data-stu-id="3994f-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="3994f-172">Di conseguenza, il rilascio dell'istanza del servizio comporta il completamento della transazione vanificando in modo prematuro l'effettivo uso del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="3994f-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="3994f-173">Se questa proprietà è impostata su `true` e all'endpoint viene aggiunto il comportamento del batch transazionale, il comportamento di convalida batch genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3994f-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 <span data-ttu-id="3994f-174">La classe `Orders` incapsula l'elaborazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3994f-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="3994f-175">Nell'esempio, aggiorna il database con le informazioni dell'ordine di acquisto.</span><span class="sxs-lookup"><span data-stu-id="3994f-175">In the sample, it updates the database with purchase order information.</span></span>  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 <span data-ttu-id="3994f-176">Il comportamento batch e la relativa configurazione sono specificati nella configurazione dell'applicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3994f-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="3994f-177">La dimensione di batch è un suggerimento al sistema.</span><span class="sxs-lookup"><span data-stu-id="3994f-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="3994f-178">Ad esempio, se viene specificata una dimensione di batch di 20, verrebbero letti e inviati 20 messaggi usando una singola transazione e quindi verrebbe eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="3994f-179">Vi sono però casi in cui la transazione può eseguire il commit del batch prima che venga raggiunta la dimensione di batch.</span><span class="sxs-lookup"><span data-stu-id="3994f-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="3994f-180">A ogni transazione è associato un timeout che inizia il ciclo quando viene creata la transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="3994f-181">Quando il timeout scade la transazione viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="3994f-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="3994f-182">È possibile che il timeout scada anche prima che venga raggiunta la dimensione di batch.</span><span class="sxs-lookup"><span data-stu-id="3994f-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="3994f-183">Per evitare la rielaborazione del batch a causa dell'interruzione `TransactedBatchingBehavior` verifica il tempo residuo nella transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="3994f-184">Se è stato usato l'80% del timeout della transazione, viene eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="3994f-185">Se nella coda non sono più presenti messaggi, invece di attendere il raggiungimento della dimensione di batch <xref:System.ServiceModel.Description.TransactedBatchingBehavior> esegue il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="3994f-186">La scelta della dimensione di batch dipende dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="3994f-187">Se la dimensione di batch è troppo piccola, è possibile che non si ottengano le prestazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="3994f-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="3994f-188">Se invece la dimensione di batch è troppo grande, le prestazioni potrebbero risentirne in modo negativo.</span><span class="sxs-lookup"><span data-stu-id="3994f-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="3994f-189">Ad esempio, la transazione potrebbe persistere più a lungo e attivare dei blocchi sul database oppure potrebbe passare in una situazione di deadlock, determinando la restituzione del batch e la relativa rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="3994f-190">Il client crea un ambito di transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-190">The client creates a transaction scope.</span></span> <span data-ttu-id="3994f-191">La comunicazione con la coda avviene all'interno dell'ambito della transazione, facendo in modo che venga trattata come unità atomica nella quale alla coda vengono inviati tutti i messaggi o nessuno.</span><span class="sxs-lookup"><span data-stu-id="3994f-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="3994f-192">Il commit della transazione viene eseguito chiamando <xref:System.Transactions.TransactionScope.Complete%2A> nell'ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="3994f-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
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
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="3994f-193">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="3994f-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="3994f-194">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="3994f-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="3994f-195">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="3994f-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="3994f-196">Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3994f-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="3994f-197">È possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.</span><span class="sxs-lookup"><span data-stu-id="3994f-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="3994f-198">È possibile osservare un output mobile mentre i messaggi vengono letti in un batch ed elaborati.</span><span class="sxs-lookup"><span data-stu-id="3994f-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="3994f-199">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3994f-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3994f-200">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3994f-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3994f-201">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3994f-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3994f-202">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3994f-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="3994f-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3994f-203">See Also</span></span>
