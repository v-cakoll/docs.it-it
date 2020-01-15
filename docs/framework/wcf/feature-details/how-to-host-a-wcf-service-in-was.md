---
title: 'Procedura: ospitare un servizio WCF in WAS'
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 9945e398bbd33776cce808b44388a4415da297a1
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964777"
---
# <a name="how-to-host-a-wcf-service-in-was"></a><span data-ttu-id="c3f1d-102">Procedura: ospitare un servizio WCF in WAS</span><span class="sxs-lookup"><span data-stu-id="c3f1d-102">How to: Host a WCF Service in WAS</span></span>
<span data-ttu-id="c3f1d-103">Questo argomento descrive i passaggi di base necessari per creare un servizio di attivazione dei processi di Windows (noto anche come WAS) hosted Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-103">This topic outlines the basic steps required to create a Windows Process Activation Services (also known as WAS) hosted Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="c3f1d-104">WAS è il nuovo servizio di attivazione dei processi che rappresenta una generalizzazione delle funzionalità di Internet Information Services (IIS) utilizzabili con protocolli di trasporto non HTTP.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-104">WAS is the new process activation service that is a generalization of Internet Information Services (IIS) features that work with non-HTTP transport protocols.</span></span> <span data-ttu-id="c3f1d-105">WCF utilizza l'interfaccia dell'adattatore listener per comunicare le richieste di attivazione ricevute tramite i protocolli non HTTP supportati da WCF, ad esempio TCP, named pipe e Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-105">WCF uses the listener adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, named pipes, and Message Queuing.</span></span>  
  
 <span data-ttu-id="c3f1d-106">Questa opzione di hosting richiede che i componenti di attivazione WAS vengano installati e configurati correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-106">This hosting option requires that WAS activation components are properly installed and configured, but it does not require any hosting code to be written as part of the application.</span></span> <span data-ttu-id="c3f1d-107">Per ulteriori informazioni sull'installazione e la configurazione di WAS, vedere [How to: install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-107">For more information about installing and configuring WAS, see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c3f1d-108">L'attivazione di WAS non è supportata se la pipeline di elaborazione delle richieste del server Web è impostata sulla modalità classica.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-108">WAS activation is not supported if the web server’s request processing pipeline is set to Classic mode.</span></span> <span data-ttu-id="c3f1d-109">Se è necessario utilizzare l'attivazione WAS, la pipeline di elaborazione delle richieste del server Web deve essere impostata sulla modalità integrata.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-109">The web server’s request processing pipeline must be set to Integrated mode if WAS activation is to be used.</span></span>  
  
 <span data-ttu-id="c3f1d-110">Quando un servizio WCF è ospitato in WAS, le associazioni standard vengono utilizzate nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-110">When a WCF service is hosted in WAS, the standard bindings are used in the usual way.</span></span> <span data-ttu-id="c3f1d-111">Tuttavia, quando si utilizzano <xref:System.ServiceModel.NetTcpBinding> e <xref:System.ServiceModel.NetNamedPipeBinding> per configurare un servizio ospitato in WAS, è necessario che sia rispettato un vincolo.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-111">However, when using the <xref:System.ServiceModel.NetTcpBinding> and the <xref:System.ServiceModel.NetNamedPipeBinding> to configure a WAS-hosted service, a constraint must be satisfied.</span></span> <span data-ttu-id="c3f1d-112">Quando endpoint diversi utilizzano lo stesso trasporto, le impostazioni dell'associazione devono corrispondere sulle sette proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3f1d-112">When different endpoints use the same transport, the binding settings have to match on the following seven properties:</span></span>  
  
- <span data-ttu-id="c3f1d-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="c3f1d-113">ConnectionBufferSize</span></span>  
  
- <span data-ttu-id="c3f1d-114">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="c3f1d-114">ChannelInitializationTimeout</span></span>  
  
- <span data-ttu-id="c3f1d-115">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="c3f1d-115">MaxPendingConnections</span></span>  
  
- <span data-ttu-id="c3f1d-116">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="c3f1d-116">MaxOutputDelay</span></span>  
  
- <span data-ttu-id="c3f1d-117">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="c3f1d-117">MaxPendingAccepts</span></span>  
  
- <span data-ttu-id="c3f1d-118">ConnectionPoolSettings.IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="c3f1d-118">ConnectionPoolSettings.IdleTimeout</span></span>  
  
- <span data-ttu-id="c3f1d-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c3f1d-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span></span>  
  
 <span data-ttu-id="c3f1d-120">In caso contrario, l'endpoint che viene inizializzato per primo determina sempre i valori di queste proprietà e gli endpoint aggiunti in seguito generano un'eccezione <xref:System.ServiceModel.ServiceActivationException>, se non corrispondono alle impostazioni in questione.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-120">Otherwise, the endpoint that is initialized first always determines the values of these properties, and endpoints added later throw a <xref:System.ServiceModel.ServiceActivationException> if they do not match those settings.</span></span>  
  
 <span data-ttu-id="c3f1d-121">Per la copia di origine di questo esempio, vedere [attivazione TCP](../../../../docs/framework/wcf/samples/tcp-activation.md).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-121">For the source copy of this example, see [TCP Activation](../../../../docs/framework/wcf/samples/tcp-activation.md).</span></span>  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a><span data-ttu-id="c3f1d-122">Per creare un servizio di base ospitato in WAS</span><span class="sxs-lookup"><span data-stu-id="c3f1d-122">To create a basic service hosted by WAS</span></span>  
  
1. <span data-ttu-id="c3f1d-123">Definire un contratto di servizio per il tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-123">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. <span data-ttu-id="c3f1d-124">Implementare il contratto di servizio in una classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-124">Implement the service contract in a service class.</span></span> <span data-ttu-id="c3f1d-125">Si noti che le informazioni sull'indirizzo o sull'associazione non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-125">Note that address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="c3f1d-126">Non è necessario, inoltre, scrivere codice per recuperarle dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-126">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. <span data-ttu-id="c3f1d-127">Creare un file Web.config per definire l'associazione <xref:System.ServiceModel.NetTcpBinding> che `CalculatorService` deve utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-127">Create a Web.config file to define the <xref:System.ServiceModel.NetTcpBinding> binding to be used by the `CalculatorService` endpoints.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="c3f1d-128">Creare un file Service.svc  contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-128">Create a Service.svc file that contains the following code.</span></span>  
  
   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. <span data-ttu-id="c3f1d-129">Posizionare il file Service.svc nella directory virtuale di IIS.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-129">Place the Service.svc file in your IIS virtual directory.</span></span>  
  
### <a name="to-create-a-client-to-use-the-service"></a><span data-ttu-id="c3f1d-130">Per creare un client che utilizzi il servizio</span><span class="sxs-lookup"><span data-stu-id="c3f1d-130">To create a client to use the service</span></span>  
  
1. <span data-ttu-id="c3f1d-131">Utilizzare [lo strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-131">Use [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="c3f1d-132">Il client generato contiene l'interfaccia `ICalculator` che definisce il contratto di servizio che l'implementazione del client deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-132">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. <span data-ttu-id="c3f1d-133">L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-133">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="c3f1d-134">Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-134">Note that the address and binding information is not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="c3f1d-135">Non è necessario, inoltre, scrivere codice per recuperarle dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-135">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. <span data-ttu-id="c3f1d-136">Anche la configurazione del client che utilizza la classe <xref:System.ServiceModel.NetTcpBinding> viene generata da Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-136">The configuration for the client that uses the <xref:System.ServiceModel.NetTcpBinding> is also generated by Svcutil.exe.</span></span> <span data-ttu-id="c3f1d-137">Quando si utilizza Visual Studio, questo file deve essere denominato App.config.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-137">This file should be named in the App.config file when using Visual Studio.</span></span>  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]   
  
5. <span data-ttu-id="c3f1d-138">Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-138">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. <span data-ttu-id="c3f1d-139">Compilare ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-139">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f1d-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3f1d-140">See also</span></span>

- [<span data-ttu-id="c3f1d-141">Attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="c3f1d-141">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- <span data-ttu-id="c3f1d-142">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c3f1d-142">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
