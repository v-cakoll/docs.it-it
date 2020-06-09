---
title: Architettura di attivazione WAS
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: cfbfd91f9e7bc2e1b4f8485d5ae22c1fb2b5228b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600672"
---
# <a name="was-activation-architecture"></a><span data-ttu-id="ad086-102">Architettura di attivazione WAS</span><span class="sxs-lookup"><span data-stu-id="ad086-102">WAS Activation Architecture</span></span>
<span data-ttu-id="ad086-103">In questo argomento vengono definiti e illustrati i componenti del servizio di attivazione dei processi di Windows (noto anche come WAS).</span><span class="sxs-lookup"><span data-stu-id="ad086-103">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="ad086-104">Componenti di attivazione</span><span class="sxs-lookup"><span data-stu-id="ad086-104">Activation Components</span></span>  
 <span data-ttu-id="ad086-105">WAS è costituito da numerosi componenti architettonici:</span><span class="sxs-lookup"><span data-stu-id="ad086-105">WAS consists of several architectural components:</span></span>  
  
- <span data-ttu-id="ad086-106">Adattatori listener.</span><span class="sxs-lookup"><span data-stu-id="ad086-106">Listener adapters.</span></span> <span data-ttu-id="ad086-107">Servizi di Windows che ricevono messaggi su specifici protocolli di rete e comunicano con WAS per indirizzare i messaggi in arrivo al processo di lavoro corretto.</span><span class="sxs-lookup"><span data-stu-id="ad086-107">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
- <span data-ttu-id="ad086-108">WAS.</span><span class="sxs-lookup"><span data-stu-id="ad086-108">WAS.</span></span> <span data-ttu-id="ad086-109">Servizio di Windows che gestisce la creazione e la durata dei processi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad086-109">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
- <span data-ttu-id="ad086-110">File eseguibile del processo di lavoro generico (w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="ad086-110">The generic worker process executable (w3wp.exe).</span></span>  
  
- <span data-ttu-id="ad086-111">Gestore applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ad086-111">Application manager.</span></span> <span data-ttu-id="ad086-112">Gestisce la creazione e la durata dei domini applicazione che ospitano applicazioni all'interno del processo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad086-112">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
- <span data-ttu-id="ad086-113">Gestori del protocollo.</span><span class="sxs-lookup"><span data-stu-id="ad086-113">Protocol handlers.</span></span> <span data-ttu-id="ad086-114">Componenti specifici del protocollo che vengono eseguiti nel processo di lavoro e gestiscono le comunicazioni tra il processo di lavoro e i singoli adattatori listener.</span><span class="sxs-lookup"><span data-stu-id="ad086-114">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="ad086-115">Esistono due tipi di gestori del protocollo: del processo e AppDomain.</span><span class="sxs-lookup"><span data-stu-id="ad086-115">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="ad086-116">Quando WAS attiva un'istanza del processo di lavoro, carica i gestori del protocollo del processo necessari nel processo di lavoro e utilizza il gestore applicazioni per creare un dominio applicazione per ospitare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad086-116">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="ad086-117">Il dominio applicazione carica il codice dell'applicazione e i gestori del protocollo AppDomain richiesti dai protocolli di rete utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad086-117">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 ![Screenshot che mostra l'architettura di WAS.](./media/was-activation-architecture/windows-process-application-service-architecture.gif)  
  
### <a name="listener-adapters"></a><span data-ttu-id="ad086-119">Adattatori listener</span><span class="sxs-lookup"><span data-stu-id="ad086-119">Listener Adapters</span></span>  
 <span data-ttu-id="ad086-120">Gli adattatori listener sono servizi di Windows singoli che implementano la logica di comunicazione di rete utilizzata per ricevere i messaggi tramite il protocollo di rete sul quale ascoltano.</span><span class="sxs-lookup"><span data-stu-id="ad086-120">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="ad086-121">Nella tabella seguente sono elencati gli adapter listener per i protocolli Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ad086-121">The following table lists the listener adapters for Windows Communication Foundation (WCF) protocols.</span></span>  
  
|<span data-ttu-id="ad086-122">Nome del servizio dell’adattatore listener</span><span class="sxs-lookup"><span data-stu-id="ad086-122">Listener adapter service name</span></span>|<span data-ttu-id="ad086-123">Protocollo</span><span class="sxs-lookup"><span data-stu-id="ad086-123">Protocol</span></span>|<span data-ttu-id="ad086-124">Note</span><span class="sxs-lookup"><span data-stu-id="ad086-124">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="ad086-125">W3SVC</span><span class="sxs-lookup"><span data-stu-id="ad086-125">W3SVC</span></span>|<span data-ttu-id="ad086-126">http</span><span class="sxs-lookup"><span data-stu-id="ad086-126">http</span></span>|<span data-ttu-id="ad086-127">Componente comune che fornisce l'attivazione HTTP sia per IIS 7,0 che per WCF.</span><span class="sxs-lookup"><span data-stu-id="ad086-127">Common component that provides HTTP activation for both IIS 7.0 and WCF.</span></span>|  
|<span data-ttu-id="ad086-128">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="ad086-128">NetTcpActivator</span></span>|<span data-ttu-id="ad086-129">net.tcp</span><span class="sxs-lookup"><span data-stu-id="ad086-129">net.tcp</span></span>|<span data-ttu-id="ad086-130">Dipende dal servizio NetTcpPortSharing.</span><span class="sxs-lookup"><span data-stu-id="ad086-130">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="ad086-131">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="ad086-131">NetPipeActivator</span></span>|<span data-ttu-id="ad086-132">net.pipe</span><span class="sxs-lookup"><span data-stu-id="ad086-132">net.pipe</span></span>||  
|<span data-ttu-id="ad086-133">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="ad086-133">NetMsmqActivator</span></span>|<span data-ttu-id="ad086-134">net.msmq</span><span class="sxs-lookup"><span data-stu-id="ad086-134">net.msmq</span></span>|<span data-ttu-id="ad086-135">Per l'utilizzo con le applicazioni di Accodamento messaggi basate su WCF.</span><span class="sxs-lookup"><span data-stu-id="ad086-135">For use with WCF-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="ad086-136">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="ad086-136">NetMsmqActivator</span></span>|<span data-ttu-id="ad086-137">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="ad086-137">msmq.formatname</span></span>|<span data-ttu-id="ad086-138">Fornisce la compatibilità delle applicazioni di accodamento messaggi esistenti con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ad086-138">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="ad086-139">Gli adattatori listener per protocolli specifici vengono registrati durante l'installazione nel file applicationHost.config, come illustrato nell'esempio XML seguente.</span><span class="sxs-lookup"><span data-stu-id="ad086-139">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a><span data-ttu-id="ad086-140">Gestori del protocollo</span><span class="sxs-lookup"><span data-stu-id="ad086-140">Protocol Handlers</span></span>  
 <span data-ttu-id="ad086-141">I gestori del processo e del protocollo AppDomain per protocolli specifici vengono registrati nel file Web.config a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="ad086-141">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad086-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad086-142">See also</span></span>

- [<span data-ttu-id="ad086-143">Configurazione di WAS per l'uso con WCF</span><span class="sxs-lookup"><span data-stu-id="ad086-143">Configuring WAS for Use with WCF</span></span>](configuring-the-wpa--service-for-use-with-wcf.md)
- <span data-ttu-id="ad086-144">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ad086-144">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
