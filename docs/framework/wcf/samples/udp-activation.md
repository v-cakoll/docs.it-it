---
title: Attivazione UDP
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: c0b351adb0b45f42404e94c74bdcff7785c2d0ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143720"
---
# <a name="udp-activation"></a><span data-ttu-id="e6136-102">Attivazione UDP</span><span class="sxs-lookup"><span data-stu-id="e6136-102">UDP Activation</span></span>
<span data-ttu-id="e6136-103">Questo esempio è basato sull'esempio [Transport: UDP.](../../../../docs/framework/wcf/samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="e6136-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="e6136-104">Estende l'esempio [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) per supportare l'attivazione del processo tramite il servizio Attivazione processo Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="e6136-104">It extends the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample to support process activation using the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="e6136-105">L'esempio è costituito da tre parti principali:</span><span class="sxs-lookup"><span data-stu-id="e6136-105">The sample consists of three major pieces:</span></span>  
  
- <span data-ttu-id="e6136-106">Un attivatore del protocollo UDP, un processo autonomo che riceve messaggi UDP per conto delle applicazioni che devono essere attivate.</span><span class="sxs-lookup"><span data-stu-id="e6136-106">A UDP Protocol Activator, a standalone process that receives UDP messages on behalf of applications that are to be activated.</span></span>  
  
- <span data-ttu-id="e6136-107">Un client che utilizza il trasporto personalizzato UDP per inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="e6136-107">A client that uses the UDP custom transport to send messages.</span></span>  
  
- <span data-ttu-id="e6136-108">Un servizio (ospitato in un processo di lavoro attivato da WAS) che riceve messaggi sul trasporto personalizzato UDP.</span><span class="sxs-lookup"><span data-stu-id="e6136-108">A service (hosted in a worker process activated by WAS) that receives messages over the UDP custom transport.</span></span>  
  
## <a name="udp-protocol-activator"></a><span data-ttu-id="e6136-109">Attivatore del protocollo UDP</span><span class="sxs-lookup"><span data-stu-id="e6136-109">UDP Protocol Activator</span></span>  
 <span data-ttu-id="e6136-110">L'attivatore di protocollo UDP è un ponte tra il client WCF e il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="e6136-110">The UDP Protocol Activator is a bridge between the WCF client and the WCF service.</span></span> <span data-ttu-id="e6136-111">Fornisce la comunicazione dati tramite il protocollo UDP a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="e6136-111">It provides data communication through the UDP protocol at the transport layer.</span></span> <span data-ttu-id="e6136-112">e ha due funzioni principali:</span><span class="sxs-lookup"><span data-stu-id="e6136-112">It has two major functions:</span></span>  
  
- <span data-ttu-id="e6136-113">Adattatore listener (LA) WAS, che collabora con WAS per attivare processi in risposta ai messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e6136-113">WAS Listener Adapter (LA), which collaborates with WAS to activate processes in response to incoming messages.</span></span>  
  
- <span data-ttu-id="e6136-114">Listener protocollo UDP, che accetta messaggi UDP per conto delle applicazioni che devono essere attivate.</span><span class="sxs-lookup"><span data-stu-id="e6136-114">UDP Protocol Listener, which accepts UDP messages on behalf of applications that are to be activated.</span></span>  
  
 <span data-ttu-id="e6136-115">L'attivatore deve essere in esecuzione come programma autonomo sul server.</span><span class="sxs-lookup"><span data-stu-id="e6136-115">The activator must be running as a standalone program on the server machine.</span></span> <span data-ttu-id="e6136-116">In genere, gli adattatori listener (ad esempio NetTcpActivator e NetPipeActivator) vengono implementati nei servizi Windows di lunga durata.</span><span class="sxs-lookup"><span data-stu-id="e6136-116">Normally, WAS listener adapters (such as the NetTcpActivator and the NetPipeActivator) are implemented in long-running Windows services.</span></span> <span data-ttu-id="e6136-117">Tuttavia, per maggiore semplicità e chiarezza, questo esempio implementa l'attivatore del protocollo come applicazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="e6136-117">However, for simplicity and clarity, this sample implements the protocol activator as a standalone application.</span></span>  
  
### <a name="was-listener-adapter"></a><span data-ttu-id="e6136-118">Adattatore listener WAS</span><span class="sxs-lookup"><span data-stu-id="e6136-118">WAS Listener Adapter</span></span>  
 <span data-ttu-id="e6136-119">L'adattatore listener WAS per UDP è implementato nella classe `UdpListenerAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e6136-119">The WAS Listener Adapter for UDP is implemented in the `UdpListenerAdapter` class.</span></span> <span data-ttu-id="e6136-120">È il modulo che interagisce con WAS per eseguire l'attivazione dell'applicazione per il protocollo UDP.</span><span class="sxs-lookup"><span data-stu-id="e6136-120">It is the module that interacts with WAS to perform application activation for the UDP protocol.</span></span> <span data-ttu-id="e6136-121">Questo risultato viene ottenuto chiamando le seguenti API Webhost:</span><span class="sxs-lookup"><span data-stu-id="e6136-121">This is achieved by calling the following Webhost APIs:</span></span>  
  
- `WebhostRegisterProtocol`  
  
- `WebhostUnregisterProtocol`  
  
- `WebhostOpenListenerChannelInstance`  
  
- `WebhostCloseAllListenerChannelInstances`  
  
 <span data-ttu-id="e6136-122">Dopo la chiamata iniziale a `WebhostRegisterProtocol`, l'adattatore del listener riceve l'elemento `ApplicationCreated` callback da WAS per tutte le applicazioni registrate in applicationHost.config (in %windir%\system32\inetsrv).</span><span class="sxs-lookup"><span data-stu-id="e6136-122">After initially calling `WebhostRegisterProtocol`, the listener adapter receives the callback `ApplicationCreated` from WAS for all of the applications registered in applicationHost.config (located in %windir%\system32\inetsrv).</span></span> <span data-ttu-id="e6136-123">In questo esempio, vengono gestite solo le applicazioni con il protocollo UDP (con l'ID del protocollo "net.udp") abilitato.</span><span class="sxs-lookup"><span data-stu-id="e6136-123">In this sample, we only handle the applications with the UDP protocol (with the protocol id as "net.udp") enabled.</span></span> <span data-ttu-id="e6136-124">Altre implementazioni possono gestire questo contesto in modo diverso se tali implementazioni rispondono alle modifiche dinamiche di configurazione all'applicazione (ad esempio, una transizione dell'applicazione da disabilitata ad abilitata).</span><span class="sxs-lookup"><span data-stu-id="e6136-124">Other implementations may handle this differently if such implementations respond to dynamic configuration changes to the application (for example, an application transition from disabled to enabled).</span></span>  
  
 <span data-ttu-id="e6136-125">Quando si riceve l'elemento `ConfigManagerInitializationCompleted` di callback, ciò indica che WAS ha completato tutte le notifiche per l'inizializzazione del protocollo.</span><span class="sxs-lookup"><span data-stu-id="e6136-125">When the callback `ConfigManagerInitializationCompleted` is received, it indicates that WAS has finished all of the notifications for the initialization of the protocol.</span></span> <span data-ttu-id="e6136-126">A questo punto, l'adattatore del listener è pronto per elaborare le richieste di attivazione.</span><span class="sxs-lookup"><span data-stu-id="e6136-126">At this time, the listener adapter is ready to process activation requests.</span></span>  
  
 <span data-ttu-id="e6136-127">Quando una nuova richiesta viene ricevuta per la prima volta per un'applicazione, l'adattatore del listener chiama `WebhostOpenListenerChannelInstance` in WAS per avviare il processo di lavoro, se non è ancora stato avviato.</span><span class="sxs-lookup"><span data-stu-id="e6136-127">When a new request comes in the first time for an application, the listener adapter calls `WebhostOpenListenerChannelInstance` into WAS, which starts the worker process if it is not started yet.</span></span> <span data-ttu-id="e6136-128">I gestori del protocollo vengono quindi caricati e la comunicazione tra l'adattatore del listener e l'applicazione virtuale può avere inizio.</span><span class="sxs-lookup"><span data-stu-id="e6136-128">Then the protocol handlers are loaded and the communication between the listener adapter and the virtual application can start.</span></span>  
  
 <span data-ttu-id="e6136-129">L'adattatore listener è registrato nella sezione> %SystemRoot%, System32, `listenerAdapters` Inetsrv, ApplicationHost.config nella sezione> <come segue:</span><span class="sxs-lookup"><span data-stu-id="e6136-129">The listener adapter is registered in the %SystemRoot%\System32\inetsrv\ApplicationHost.config in the <`listenerAdapters`> section as following:</span></span>  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a><span data-ttu-id="e6136-130">Listener del protocollo</span><span class="sxs-lookup"><span data-stu-id="e6136-130">Protocol Listener</span></span>  
 <span data-ttu-id="e6136-131">Il listener del protocollo UDP è un modulo all'interno dell'attivatore del protocollo che è in ascolto su un endpoint UDP per conto dell'applicazione virtuale,</span><span class="sxs-lookup"><span data-stu-id="e6136-131">The UDP protocol listener is a module inside the protocol activator that listens at a UDP endpoint on behalf of the virtual application.</span></span> <span data-ttu-id="e6136-132">ed è implementato nella classe `UdpSocketListener`.</span><span class="sxs-lookup"><span data-stu-id="e6136-132">It is implemented in the class `UdpSocketListener`.</span></span> <span data-ttu-id="e6136-133">L'endpoint è rappresentato come `IPEndpoint` per il quale viene estratto il numero della porta dall'associazione del protocollo per il sito.</span><span class="sxs-lookup"><span data-stu-id="e6136-133">The endpoint is represented as `IPEndpoint` for which the port number is extracted from the binding of the protocol for the site.</span></span>  
  
### <a name="control-service"></a><span data-ttu-id="e6136-134">Servizio di controllo</span><span class="sxs-lookup"><span data-stu-id="e6136-134">Control Service</span></span>  
 <span data-ttu-id="e6136-135">In questo esempio viene usato WCF per comunicare tra l'attivatore e il processo di lavoro WAS.</span><span class="sxs-lookup"><span data-stu-id="e6136-135">In this sample, we use WCF to communicate between the activator and the WAS worker process.</span></span> <span data-ttu-id="e6136-136">Il servizio che si trova risiede nell'attivatore è definito servizio di controllo.</span><span class="sxs-lookup"><span data-stu-id="e6136-136">The service that resides in the activator is called the Control Service.</span></span>  
  
## <a name="protocol-handlers"></a><span data-ttu-id="e6136-137">Gestori del protocollo</span><span class="sxs-lookup"><span data-stu-id="e6136-137">Protocol Handlers</span></span>  
 <span data-ttu-id="e6136-138">Quando l'adattatore del listener chiama `WebhostOpenListenerChannelInstance`, la gestione processi WAS avvia il processo di lavoro, se non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="e6136-138">After the listener adapter calls `WebhostOpenListenerChannelInstance`, the WAS process manager starts the worker process if it is not started.</span></span> <span data-ttu-id="e6136-139">La gestione applicazioni nel processo di lavoro carica quindi il gestore del protocollo del processo (PPH, Process Protocol Handler) di UDP con la richiesta per tale `ListenerChannelId`.</span><span class="sxs-lookup"><span data-stu-id="e6136-139">The application manager inside the worker process then loads the UDP Process Protocol Handler (PPH) with the request for that `ListenerChannelId`.</span></span> <span data-ttu-id="e6136-140">Il PPH chiama `IAdphManager`a sua volta .`StartAppDomainProtocolListenerChannel`</span><span class="sxs-lookup"><span data-stu-id="e6136-140">The PPH in turns calls `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span></span> <span data-ttu-id="e6136-141">per avviare il gestore protocollo AppDomain UDP (ADPH).</span><span class="sxs-lookup"><span data-stu-id="e6136-141">to start the UDP AppDomain Protocol Handler (ADPH).</span></span>  
  
## <a name="hostedudptransportconfiguration"></a><span data-ttu-id="e6136-142">HostedUDPTransportConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6136-142">HostedUDPTransportConfiguration</span></span>  
 <span data-ttu-id="e6136-143">Le informazioni vengono registrate in Web.config come segue:</span><span class="sxs-lookup"><span data-stu-id="e6136-143">The information is registered in the Web.config as follows:</span></span>  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a><span data-ttu-id="e6136-144">Installazione speciale per questo esempio</span><span class="sxs-lookup"><span data-stu-id="e6136-144">Special Setup for This Sample</span></span>  
 <span data-ttu-id="e6136-145">Questo esempio può essere compilato ed eseguito solo in Windows Vista, Windows Server 2008 o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e6136-145">This sample can be only built and run on Windows Vista, Windows Server 2008, or Windows 7.</span></span> <span data-ttu-id="e6136-146">Per eseguire l'esempio, impostare prima tutti i componenti correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6136-146">To run the sample, you must first get all of the components set up correctly.</span></span> <span data-ttu-id="e6136-147">Utilizzare i passaggi seguenti per installare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e6136-147">Use the following steps to install the sample.</span></span>  
  
#### <a name="to-set-up-this-sample"></a><span data-ttu-id="e6136-148">Per impostare questo esempio</span><span class="sxs-lookup"><span data-stu-id="e6136-148">To set up this sample</span></span>  
  
1. <span data-ttu-id="e6136-149">Installare ASP.NET 4.0 utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e6136-149">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="e6136-150">Compilare il progetto su Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e6136-150">Build the project on Windows Vista.</span></span> <span data-ttu-id="e6136-151">Dopo la compilazione, vengono eseguite anche le operazioni seguenti nella fase post-compilazione:</span><span class="sxs-lookup"><span data-stu-id="e6136-151">After compilation, it also performs the following operations in the post-build phase:</span></span>  
  
    - <span data-ttu-id="e6136-152">Installa l'associazione UDP al sito "Sito Web predefinito".</span><span class="sxs-lookup"><span data-stu-id="e6136-152">Installs the UDP binding to the site "Default Web Site".</span></span>  
  
    - <span data-ttu-id="e6136-153">Crea l'applicazione virtuale "ServiceModelSamples" per puntare al percorso fisico: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span><span class="sxs-lookup"><span data-stu-id="e6136-153">Creates the virtual application "ServiceModelSamples" to point to the physical path: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span></span>  
  
    - <span data-ttu-id="e6136-154">Abilita anche il protocollo "net.udp" per questa applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="e6136-154">It also enables "net.udp" protocol for this virtual application.</span></span>  
  
3. <span data-ttu-id="e6136-155">Avviare l'applicazione dell'interfaccia utente "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="e6136-155">Start the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e6136-156">Fare clic sulla scheda **Configurazione,** selezionare le seguenti caselle di controllo e quindi fare clic su **Installa** per installarle:</span><span class="sxs-lookup"><span data-stu-id="e6136-156">Click the **Setup** tab, check the following check boxes and then click **Install** to install them:</span></span>  
  
    - <span data-ttu-id="e6136-157">Adattatore listener UDP</span><span class="sxs-lookup"><span data-stu-id="e6136-157">UDP Listener Adapter</span></span>  
  
    - <span data-ttu-id="e6136-158">Gestori del protocollo UDP</span><span class="sxs-lookup"><span data-stu-id="e6136-158">UDP Protocol Handlers</span></span>  
  
4. <span data-ttu-id="e6136-159">Fare clic sulla scheda **Attivazione** dell'applicazione dell'interfaccia utente "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="e6136-159">Click the **Activation** tab of the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e6136-160">Fare clic sul pulsante **Start** per avviare l'adattatore listener.</span><span class="sxs-lookup"><span data-stu-id="e6136-160">Click the **Start** button to start the listener adapter.</span></span> <span data-ttu-id="e6136-161">È ora possibile eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="e6136-161">Now you are ready to run the program.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e6136-162">Dopo aver concluso l'esempio, è necessario eseguire Cleanup.bat per rimuovere l'associazione net.udp dal "Sito Web predefinito".</span><span class="sxs-lookup"><span data-stu-id="e6136-162">When you are finished with this sample, you must run Cleanup.bat to remove the net.udp binding from the "Default Web Site".</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="e6136-163">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="e6136-163">Sample Usage</span></span>  
 <span data-ttu-id="e6136-164">Dopo la compilazione, vengono generati quattro file binari diversi:</span><span class="sxs-lookup"><span data-stu-id="e6136-164">After compilation, there are four different binaries generated:</span></span>  
  
- <span data-ttu-id="e6136-165">Client.exe: il codice del client.</span><span class="sxs-lookup"><span data-stu-id="e6136-165">Client.exe: The client code.</span></span> <span data-ttu-id="e6136-166">Il file App.config viene compilato nel file di configurazione del client Client.exe.config.</span><span class="sxs-lookup"><span data-stu-id="e6136-166">The App.config is compiled into the client configuration file Client.exe.config.</span></span>  
  
- <span data-ttu-id="e6136-167">UDPActivation.dll: la libreria che contiene tutte le principali implementazioni UDP.</span><span class="sxs-lookup"><span data-stu-id="e6136-167">UDPActivation.dll: the library that contains all of the major UDP implementations.</span></span>  
  
- <span data-ttu-id="e6136-168">Service.dll: il codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="e6136-168">Service.dll: The service code.</span></span> <span data-ttu-id="e6136-169">Questo file viene copiato nella directory \bin dell'applicazione virtuale ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="e6136-169">This is copied to the \bin directory of the virtual application ServiceModelSamples.</span></span> <span data-ttu-id="e6136-170">Il file del servizio è Service.svc e il file di configurazione è Web.config. Dopo la compilazione, vengono copiati nel seguente percorso: %SystemDrive%</span><span class="sxs-lookup"><span data-stu-id="e6136-170">The service file is Service.svc and the configuration file is Web.config. After compilation, they are copied to the following location: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span></span>  
  
- <span data-ttu-id="e6136-171">WasNetActivator: il programma attivatore di UDP.</span><span class="sxs-lookup"><span data-stu-id="e6136-171">WasNetActivator: The UDP activator program.</span></span>  
  
- <span data-ttu-id="e6136-172">Verificare che tutte le parti necessarie siano installate correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6136-172">Ensure that all of the required pieces are installed correctly.</span></span> <span data-ttu-id="e6136-173">Nei passaggi seguenti viene illustrato come eseguire l'esempio:</span><span class="sxs-lookup"><span data-stu-id="e6136-173">The following steps show how to run the sample:</span></span>  
  
1. <span data-ttu-id="e6136-174">Verificare che i servizi Windows seguenti siano stati avviati:</span><span class="sxs-lookup"><span data-stu-id="e6136-174">Ensure that the following Windows services have been started:</span></span>  
  
    - <span data-ttu-id="e6136-175">Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service).</span><span class="sxs-lookup"><span data-stu-id="e6136-175">Windows Process Activation Service (WAS).</span></span>  
  
    - <span data-ttu-id="e6136-176">Internet Information Services (IIS): W3SVC.</span><span class="sxs-lookup"><span data-stu-id="e6136-176">Internet Information Services (IIS): W3SVC.</span></span>  
  
2. <span data-ttu-id="e6136-177">Quindi avviare l'attivatore, WasNetActivator.exe.</span><span class="sxs-lookup"><span data-stu-id="e6136-177">Then start the activator, WasNetActivator.exe.</span></span> <span data-ttu-id="e6136-178">**Nell'elenco** a discesa è selezionato l'unico protocollo **UDP**.</span><span class="sxs-lookup"><span data-stu-id="e6136-178">Under the **Activation** tab, the only protocol, **UDP**, is selected in the drop down list.</span></span> <span data-ttu-id="e6136-179">Fare clic sul pulsante **Start** per avviare l'attivatore.</span><span class="sxs-lookup"><span data-stu-id="e6136-179">Click the **Start** button to start the activator.</span></span>  
  
3. <span data-ttu-id="e6136-180">Quando l'attivatore è stato avviato, è possibile eseguire il codice client eseguendo Client.exe da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="e6136-180">Once the activator is started, you can run the client code by running Client.exe from a command window.</span></span> <span data-ttu-id="e6136-181">Di seguito è riportato un output di esempio:</span><span class="sxs-lookup"><span data-stu-id="e6136-181">The following is the sample output:</span></span>  
  
    ```console  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
> <span data-ttu-id="e6136-182">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e6136-182">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6136-183">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e6136-183">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e6136-184">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e6136-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6136-185">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e6136-185">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
