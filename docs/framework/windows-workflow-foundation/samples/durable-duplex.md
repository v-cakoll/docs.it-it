---
title: Duplex durevole
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 107c617fa4a8ee0279dcaa07e495587c617b866e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513353"
---
# <a name="durable-duplex"></a><span data-ttu-id="a71ba-102">Duplex durevole</span><span class="sxs-lookup"><span data-stu-id="a71ba-102">Durable Duplex</span></span>
<span data-ttu-id="a71ba-103">In questo esempio viene illustrato come impostare e configurare lo scambio durevole di messaggi duplex usando le attività di messaggistica in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="a71ba-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="a71ba-104">Un scambio durevole di messaggi duplex è un scambio di messaggi bidirezionale che si verifica in un lungo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="a71ba-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="a71ba-105">È possibile che la durata dello scambio di messaggi sia superiore alla durata del canale di comunicazione e alla durata in memoria delle istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="a71ba-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a71ba-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="a71ba-106">Sample Details</span></span>  
 <span data-ttu-id="a71ba-107">In questo esempio, due servizi Windows Communication Foundation (WCF) implementati utilizzando Windows Workflow Foundation sono configurati per avere un scambio durevole di messaggi duplex.</span><span class="sxs-lookup"><span data-stu-id="a71ba-107">In this sample, two Windows Communication Foundation (WCF) services implemented using Windows Workflow Foundation are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="a71ba-108">Lo scambio durevole di messaggi duplex è composto da due messaggi unidirezionali inviati tramite MSMQ e correlati usando [scambio del contesto .NET](https://go.microsoft.com/fwlink/?LinkID=166059).</span><span class="sxs-lookup"><span data-stu-id="a71ba-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](https://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="a71ba-109">I messaggi vengono inviati tramite le attività di messaggistica <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="a71ba-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="a71ba-110">Lo scambio del contesto di .NET viene usato per specificare l'indirizzo di callback nei messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="a71ba-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="a71ba-111">Entrambi i servizi sono ospitati tramite i servizi Attivazione processo Windows (WAS) e sono configurati per abilitare la persistenza delle istanze dei servizi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="a71ba-112">Il primo servizio (Service1.xamlx) invia una richiesta al servizio di invio (Service2.xamlx) per l'esecuzione di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="a71ba-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="a71ba-113">Al termine, per indicare che l'operazione è stata completata, Service2.xamlx restituisce una notifica a Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a71ba-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="a71ba-114">Un'applicazione console del flusso di lavoro configura le code su cui i servizi sono in ascolto e invia il messaggio di avvio per l'attivazione di Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a71ba-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="a71ba-115">Una volta che Service1.xamlx ha ricevuto da Service2.xamlx la notifica che l'operazione richiesta è stata completata, il risultato viene salvato da Service1.xamlx in un file XML.</span><span class="sxs-lookup"><span data-stu-id="a71ba-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="a71ba-116">In attesa del messaggio di callback, Service1.xamlx salva in modo permanente lo stato dell'istanza usando l'oggetto <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> predefinito.</span><span class="sxs-lookup"><span data-stu-id="a71ba-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="a71ba-117">Service2.xamlx salva in modo permanente lo stato dell'istanza come parte del completamento dell'operazione richiesta da Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a71ba-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="a71ba-118">Per fare in modo che venga usato lo scambio del contesto di .NET su MSMQ, entrambi i servizi sono configurati per l'uso di un'associazione personalizzata costituita da <xref:System.ServiceModel.Channels.ContextBindingElement> e <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a71ba-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="a71ba-119">Un indirizzo di callback viene specificato con <xref:System.ServiceModel.Channels.ContextBindingElement> ed è incluso in un'intestazione del contesto di callback con tutti i messaggi inviati usando un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a71ba-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="a71ba-120">Nel codice seguente viene definita l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a71ba-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="a71ba-121">L'associazione usata da questo esempio non è sicura.</span><span class="sxs-lookup"><span data-stu-id="a71ba-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="a71ba-122">In caso di distribuzione dell'applicazione è necessario configurare l'associazione in base ai requisiti di sicurezza dell'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="a71ba-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a71ba-123">Le code usate in questo esempio non sono transazionali.</span><span class="sxs-lookup"><span data-stu-id="a71ba-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="a71ba-124">Per un esempio che illustra come configurare lo scambio di messaggi WCF usando code di transazioni, vedere la [attivazione MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="a71ba-124">For a sample that shows how to set up WCF message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="a71ba-125">Per l'invio del messaggio da Service1.xamlx a Service2.xamlx viene usato un endpoint client configurato con l'indirizzo di Service2.xamlx e con l'associazione personalizzata definita precedentemente.</span><span class="sxs-lookup"><span data-stu-id="a71ba-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="a71ba-126">Il callback da Service2.xamlx a Service1.xamlx viene inviato usando un endpoint client senza indirizzo configurato in modo esplicito, perché l'indirizzo viene rilevato dal contesto di callback inviato da Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a71ba-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="a71ba-127">Nel codice seguente vengono definiti gli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="a71ba-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a71ba-128">Nell'esempio di codice seguente vengono esposti endpoint tramite questa associazione personalizzata modificando il mapping del protocollo predefinito per gli indirizzi di base net.msmq, in modo che venga usata l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a71ba-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a71ba-129">Nell'esempio di codice seguente viene abilitata la persistenza per entrambi i servizi aggiungendo agli stessi il comportamento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> e specificando la stringa di connessione per il database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="a71ba-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="a71ba-130">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="a71ba-130">System Requirements</span></span>  
 <span data-ttu-id="a71ba-131">Per questo esempio sono richiesti i componenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a71ba-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="a71ba-132">Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="a71ba-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="a71ba-133">Internet Information Services -> Compatibilità di gestione con IIS 6.0 -> Compatibilità metabase di IIS e configurazione di IIS 6.0.</span><span class="sxs-lookup"><span data-stu-id="a71ba-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="a71ba-134">Servizi World Wide Web -> Funzionalità per lo sviluppo di applicazioni -> ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a71ba-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="a71ba-135">Microsoft Message Queuing (MSMQ) Server.</span><span class="sxs-lookup"><span data-stu-id="a71ba-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a71ba-136">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a71ba-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="a71ba-137">Impostare il database di persistenza e la directory dei risultati.</span><span class="sxs-lookup"><span data-stu-id="a71ba-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="a71ba-138">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a71ba-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="a71ba-139">Passare alla cartella di questo esempio ed eseguire Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a71ba-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="a71ba-140">Impostare l'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="a71ba-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="a71ba-141">Da un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] registrare ASP.NET tramite il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a71ba-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="a71ba-142">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni di amministratore facendo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="a71ba-143">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file DurableDuplex.sln.</span><span class="sxs-lookup"><span data-stu-id="a71ba-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="a71ba-144">Impostare le code del servizio:</span><span class="sxs-lookup"><span data-stu-id="a71ba-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="a71ba-145">Per eseguire il client DurableDuplex, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a71ba-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="a71ba-146">Aprire il **Gestione Computer** console eseguendo `Compmgmt.msc` da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="a71ba-147">Espandere **applicazioni e servizi**, **Accodamento**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="a71ba-148">**Code private**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="a71ba-149">Le code durableduplex/service1.xamlx e durableduplex/service2.xamlx e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="a71ba-150">Selezionare il **sicurezza** scheda e consentire **tutti gli utenti ricevono messaggi**, **Visualizza il messaggio** e **invio messaggio** le autorizzazioni per entrambe le code.</span><span class="sxs-lookup"><span data-stu-id="a71ba-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="a71ba-151">Aprire Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a71ba-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="a71ba-152">Passare a **Server**, **siti**, **Default Web site**, **privata**, **Duplex durevole** e selezionare **Le opzioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="a71ba-153">Modifica il **protocolli abilitati** al **MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="a71ba-154">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="a71ba-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="a71ba-155">Passare a http://localhost/private/durableduplex/service1.xamlx e http://localhost/private/durableduplex/service2.xamlx per assicurarsi che entrambi i servizi siano in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a71ba-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="a71ba-156">Premere F5 per eseguire DurableDuplexClient.</span><span class="sxs-lookup"><span data-stu-id="a71ba-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="a71ba-157">Quando lo scambio durevole di messaggi duplex è completato, viene salvato un file result.xml nella cartella C:\Inbox contenente il risultato dello scambio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="a71ba-158">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a71ba-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="a71ba-159">Eseguire Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a71ba-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="a71ba-160">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a71ba-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="a71ba-161">Passare alla cartella di questo esempio ed eseguire Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a71ba-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="a71ba-162">Rimuovere l'applicazione virtuale per i servizi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="a71ba-163">Aprire Gestione Internet Information Services (IIS) eseguendo `Inetmgr.exe` da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="a71ba-164">Passare al sito Web predefinito e rimuovere i **privato** directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="a71ba-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="a71ba-165">Rimuovere le code impostate per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="a71ba-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="a71ba-166">Aprire la console Gestione Computer eseguendo `Compmgmt.msc` da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="a71ba-167">Espandere **applicazioni e servizi**, **Accodamento**, **code Private**.</span><span class="sxs-lookup"><span data-stu-id="a71ba-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="a71ba-168">Eliminare le code durableduplex/service1.xamlx e durableduplex/service2.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a71ba-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="a71ba-169">Rimuovere la directory C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="a71ba-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a71ba-170">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a71ba-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a71ba-171">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a71ba-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a71ba-172">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a71ba-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a71ba-173">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a71ba-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`