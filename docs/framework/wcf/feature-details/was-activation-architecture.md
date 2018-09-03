---
title: Architettura di attivazione WAS
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: 64219649e7b743b7dd3a67673c3f2409aeeba486
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43457160"
---
# <a name="was-activation-architecture"></a><span data-ttu-id="7754e-102">Architettura di attivazione WAS</span><span class="sxs-lookup"><span data-stu-id="7754e-102">WAS Activation Architecture</span></span>
<span data-ttu-id="7754e-103">In questo argomento vengono definiti e illustrati i componenti del servizio di attivazione dei processi di Windows (noto anche come WAS).</span><span class="sxs-lookup"><span data-stu-id="7754e-103">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="7754e-104">Componenti di attivazione</span><span class="sxs-lookup"><span data-stu-id="7754e-104">Activation Components</span></span>  
 <span data-ttu-id="7754e-105">WAS è costituito da numerosi componenti architettonici:</span><span class="sxs-lookup"><span data-stu-id="7754e-105">WAS consists of several architectural components:</span></span>  
  
-   <span data-ttu-id="7754e-106">Adattatori listener.</span><span class="sxs-lookup"><span data-stu-id="7754e-106">Listener adapters.</span></span> <span data-ttu-id="7754e-107">Servizi di Windows che ricevono messaggi su specifici protocolli di rete e comunicano con WAS per indirizzare i messaggi in arrivo al processo di lavoro corretto.</span><span class="sxs-lookup"><span data-stu-id="7754e-107">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
-   <span data-ttu-id="7754e-108">WAS.</span><span class="sxs-lookup"><span data-stu-id="7754e-108">WAS.</span></span> <span data-ttu-id="7754e-109">Servizio di Windows che gestisce la creazione e la durata dei processi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7754e-109">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
-   <span data-ttu-id="7754e-110">File eseguibile del processo di lavoro generico (w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="7754e-110">The generic worker process executable (w3wp.exe).</span></span>  
  
-   <span data-ttu-id="7754e-111">Gestore applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7754e-111">Application manager.</span></span> <span data-ttu-id="7754e-112">Gestisce la creazione e la durata dei domini applicazione che ospitano applicazioni all'interno del processo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7754e-112">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
-   <span data-ttu-id="7754e-113">Gestori del protocollo.</span><span class="sxs-lookup"><span data-stu-id="7754e-113">Protocol handlers.</span></span> <span data-ttu-id="7754e-114">Componenti specifici del protocollo che vengono eseguiti nel processo di lavoro e gestiscono le comunicazioni tra il processo di lavoro e i singoli adattatori listener.</span><span class="sxs-lookup"><span data-stu-id="7754e-114">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="7754e-115">Esistono due tipi di gestori del protocollo: del processo e AppDomain.</span><span class="sxs-lookup"><span data-stu-id="7754e-115">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="7754e-116">Quando WAS attiva un'istanza del processo di lavoro, carica i gestori del protocollo del processo necessari nel processo di lavoro e utilizza il gestore applicazioni per creare un dominio applicazione per ospitare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7754e-116">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="7754e-117">Il dominio applicazione carica il codice dell'applicazione e i gestori del protocollo AppDomain richiesti dai protocolli di rete utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7754e-117">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 <span data-ttu-id="7754e-118">![Architettura WAS](../../../../docs/framework/wcf/feature-details/media/wasarchitecture.gif "WASArchitecture")</span><span class="sxs-lookup"><span data-stu-id="7754e-118">![WAS Architecture](../../../../docs/framework/wcf/feature-details/media/wasarchitecture.gif "WASArchitecture")</span></span>  
  
### <a name="listener-adapters"></a><span data-ttu-id="7754e-119">Adattatori listener</span><span class="sxs-lookup"><span data-stu-id="7754e-119">Listener Adapters</span></span>  
 <span data-ttu-id="7754e-120">Gli adattatori listener sono servizi di Windows singoli che implementano la logica di comunicazione di rete utilizzata per ricevere i messaggi tramite il protocollo di rete sul quale ascoltano.</span><span class="sxs-lookup"><span data-stu-id="7754e-120">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="7754e-121">La tabella seguente elenca gli adattatori listener per i protocolli di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7754e-121">The following table lists the listener adapters for Windows Communication Foundation (WCF) protocols.</span></span>  
  
|<span data-ttu-id="7754e-122">Nome del servizio dell’adattatore listener</span><span class="sxs-lookup"><span data-stu-id="7754e-122">Listener adapter service name</span></span>|<span data-ttu-id="7754e-123">Protocollo</span><span class="sxs-lookup"><span data-stu-id="7754e-123">Protocol</span></span>|<span data-ttu-id="7754e-124">Note</span><span class="sxs-lookup"><span data-stu-id="7754e-124">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="7754e-125">W3SVC</span><span class="sxs-lookup"><span data-stu-id="7754e-125">W3SVC</span></span>|<span data-ttu-id="7754e-126">http</span><span class="sxs-lookup"><span data-stu-id="7754e-126">http</span></span>|<span data-ttu-id="7754e-127">Componente comune che fornisce l'attivazione HTTP per IIS 7.0 e WCF.</span><span class="sxs-lookup"><span data-stu-id="7754e-127">Common component that provides HTTP activation for both IIS 7.0 and WCF.</span></span>|  
|<span data-ttu-id="7754e-128">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="7754e-128">NetTcpActivator</span></span>|<span data-ttu-id="7754e-129">net.tcp</span><span class="sxs-lookup"><span data-stu-id="7754e-129">net.tcp</span></span>|<span data-ttu-id="7754e-130">Dipende dal servizio NetTcpPortSharing.</span><span class="sxs-lookup"><span data-stu-id="7754e-130">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="7754e-131">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="7754e-131">NetPipeActivator</span></span>|<span data-ttu-id="7754e-132">net.pipe</span><span class="sxs-lookup"><span data-stu-id="7754e-132">net.pipe</span></span>||  
|<span data-ttu-id="7754e-133">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="7754e-133">NetMsmqActivator</span></span>|<span data-ttu-id="7754e-134">net.msmq</span><span class="sxs-lookup"><span data-stu-id="7754e-134">net.msmq</span></span>|<span data-ttu-id="7754e-135">Per l'uso con applicazioni di Accodamento messaggi basate su WCF.</span><span class="sxs-lookup"><span data-stu-id="7754e-135">For use with WCF-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="7754e-136">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="7754e-136">NetMsmqActivator</span></span>|<span data-ttu-id="7754e-137">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="7754e-137">msmq.formatname</span></span>|<span data-ttu-id="7754e-138">Fornisce la compatibilità delle applicazioni di accodamento messaggi esistenti con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="7754e-138">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="7754e-139">Gli adattatori listener per protocolli specifici vengono registrati durante l'installazione nel file applicationHost.config, come illustrato nell'esempio XML seguente.</span><span class="sxs-lookup"><span data-stu-id="7754e-139">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
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
  
### <a name="protocol-handlers"></a><span data-ttu-id="7754e-140">Gestori del protocollo</span><span class="sxs-lookup"><span data-stu-id="7754e-140">Protocol Handlers</span></span>  
 <span data-ttu-id="7754e-141">I gestori del processo e del protocollo AppDomain per protocolli specifici vengono registrati nel file Web.config a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="7754e-141">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7754e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7754e-142">See Also</span></span>  
 [<span data-ttu-id="7754e-143">Configurazione di WAS per l'uso con WCF</span><span class="sxs-lookup"><span data-stu-id="7754e-143">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [<span data-ttu-id="7754e-144">Windows Server AppFabric con funzionalità di Hosting</span><span class="sxs-lookup"><span data-stu-id="7754e-144">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
