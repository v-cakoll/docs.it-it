---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: b1b61c18c801059e95cd0b13a3135132a583882f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183332"
---
# <a name="srmp"></a><span data-ttu-id="03105-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="03105-102">SRMP</span></span>
<span data-ttu-id="03105-103">In questo esempio viene illustrato come eseguire comunicazioni transazionali in coda usando Accodamento messaggi (MSMQ) su HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="03105-104">Nella comunicazione in coda, il client comunica al servizio usando una coda.</span><span class="sxs-lookup"><span data-stu-id="03105-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="03105-105">Più precisamente, il client invia messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="03105-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="03105-106">Il servizio riceve messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="03105-106">The service receives messages from the queue.</span></span> <span data-ttu-id="03105-107">Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="03105-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="03105-108">MSMQ consente di usare HTTP (e HTTPS) per inviare messaggi a una coda.</span><span class="sxs-lookup"><span data-stu-id="03105-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="03105-109">In questo esempio viene illustrato l'utilizzo della comunicazione in coda di Windows Communication Foundation (WCF) e come inviare messaggi tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-109">In this example, we demonstrate using Windows Communication Foundation (WCF) queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="03105-110">MSMQ usa un protocollo chiamato SRMP, protocollo basato su SOAP per la comunicazione su HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="03105-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="03105-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="03105-112">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03105-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="03105-113">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03105-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="03105-114">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="03105-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="03105-115">Prima di eseguire l'esempio in **Installazione/rimuovi componenti**di Windows , verificare che MSMQ sia installato con il supporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="03105-116">L'installazione del supporto HTTP installa automaticamente Internet Information Services (IIS) e aggiunge il supporto dei protocolli per MSMQ in IIS.</span><span class="sxs-lookup"><span data-stu-id="03105-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5. <span data-ttu-id="03105-117">Per essere sicuri che venga usato HTTP per la comunicazione, è possibile abilitare MSMQ per l'esecuzione in modalità di protezione avanzata.</span><span class="sxs-lookup"><span data-stu-id="03105-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="03105-118">In questo modo si garantisce che i messaggi inviati alla coda sul computer ospitato usando un trasporto diverso da HTTP non arrivino a destinazione.</span><span class="sxs-lookup"><span data-stu-id="03105-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6. <span data-ttu-id="03105-119">Dopo aver selezionato MSMQ per l'esecuzione in modalità con protezione dati, il computer richiede un avvio in Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="03105-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on Windows Server 2003.</span></span>  
  
7. <span data-ttu-id="03105-120">Eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="03105-120">Run the service.</span></span>  
  
8. <span data-ttu-id="03105-121">Eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="03105-121">Run the client.</span></span> <span data-ttu-id="03105-122">Assicurarsi di modificare l'indirizzo endpoint in modo che punti al nome del computer o all'indirizzo IP, anziché a localhost.</span><span class="sxs-lookup"><span data-stu-id="03105-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="03105-123">Il client invia un messaggio e viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="03105-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03105-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03105-124">Requirements</span></span>  
 <span data-ttu-id="03105-125">Per eseguire questo esempio è necessario che, oltre a MSMQ, IIS sia installato sul computer del servizio e su quello del client,</span><span class="sxs-lookup"><span data-stu-id="03105-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="03105-126">Dimostra</span><span class="sxs-lookup"><span data-stu-id="03105-126">Demonstrates</span></span>  
 <span data-ttu-id="03105-127">Nell'esempio viene illustrato l'invio di messaggi in coda WCF tramite MSMQ su HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-127">The sample demonstrates sending WCF queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="03105-128">Questa procedura viene anche chiamata messaggistica SRMP.</span><span class="sxs-lookup"><span data-stu-id="03105-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="03105-129">Quando viene inviato un messaggio in coda, MSMQ sul computer mittente trasferisce i messaggi al gestore code di destinazione usando il trasporto TCP o HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="03105-130">Se sceglie SRMP, l'utente sceglie HTTP come tipo di trasporto per il trasferimento della coda.</span><span class="sxs-lookup"><span data-stu-id="03105-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="03105-131">Il protocollo SRMP protetto consente l'uso di HTTPS.</span><span class="sxs-lookup"><span data-stu-id="03105-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03105-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="03105-132">Example</span></span>  
 <span data-ttu-id="03105-133">L'esempio di codice si basa sull'esempio transazionale.</span><span class="sxs-lookup"><span data-stu-id="03105-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="03105-134">L'invio di un messaggio alla coda e la ricezione di un messaggio dalla coda mediante SRMP sono uguali all'invio e alla ricezione di messaggi mediante un protocollo nativo.</span><span class="sxs-lookup"><span data-stu-id="03105-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="03105-135">La configurazione per il client viene modificata per indicare la scelta del protocollo di trasferimento dalla coda.</span><span class="sxs-lookup"><span data-stu-id="03105-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="03105-136">Il protocollo di trasferimento dalla coda può essere nativo, SRMP o SrmpSecure.</span><span class="sxs-lookup"><span data-stu-id="03105-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="03105-137">Per impostazione predefinita, il protocollo di trasferimento è nativo.</span><span class="sxs-lookup"><span data-stu-id="03105-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="03105-138">Nella configurazione di questo esempio il client e il servizio specificano di usare SRMP.</span><span class="sxs-lookup"><span data-stu-id="03105-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="03105-139">L'uso del protocollo SRMP presenta alcuni limiti relativi alla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="03105-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="03105-140">La sicurezza del trasporto MSMQ predefinita richiede Active Directory che richiede a sua volta che il gestore delle code mittente e il gestore delle code di destinazione risiedano nello stesso dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="03105-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="03105-141">Questo non è possibile quando si inviano messaggi mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="03105-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="03105-142">Per questa ragione, la sicurezza del trasporto predefinita non funziona.</span><span class="sxs-lookup"><span data-stu-id="03105-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="03105-143">Se si desidera che il trasporto sia protetto, è necessario impostare la sicurezza del trasporto su Certificato.</span><span class="sxs-lookup"><span data-stu-id="03105-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="03105-144">È possibile inoltre usare la sicurezza dei messaggi per proteggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="03105-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="03105-145">In questo esempio, il trasporto e la sicurezza dei messaggi sono disattivati per illustrare la messaggistica SRMP.</span><span class="sxs-lookup"><span data-stu-id="03105-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"
           bindingConfiguration="srmpBinding"
           binding="netMsmqBinding"
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="03105-146">L'esecuzione dell'esempio produce l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="03105-146">Running the sample yields the following output.</span></span>  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4
Customer: somecustomer.com
OrderDetails
    Order LineItem: 54 of Blue Widget @unit price: $29.99
    Order LineItem: 890 of Red Widget @unit price: $45.89
    Total cost of this order: $42461.56
    Order status: Pending  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="03105-147">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="03105-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03105-148">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="03105-148">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="03105-149">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="03105-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03105-150">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="03105-150">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
