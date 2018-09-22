---
title: Uso di NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: cd4a50798ff709c32db056c6aa7289993431f40e
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696742"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="4d51b-102">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4d51b-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="4d51b-103"><xref:System.ServiceModel.NetHttpBinding> è un'associazione progettata per usare i servizi HTTP o WebSocket e usa la codifica binaria per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d51b-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="4d51b-104">L'oggetto <xref:System.ServiceModel.NetHttpBinding> rileverà se viene usato con un contratto request/reply o un contratto duplex e modificherà il comportamento di conseguenza. Utilizzerà HTTP per i contratti request/reply e WebSockets per i contratti duplex.</span><span class="sxs-lookup"><span data-stu-id="4d51b-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="4d51b-105">È possibile eseguire l'override di questo comportamento usando l'impostazione <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:</span><span class="sxs-lookup"><span data-stu-id="4d51b-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="4d51b-106">`Always` -Forza WebSocket per essere usato anche per i contratti request / reply.</span><span class="sxs-lookup"><span data-stu-id="4d51b-106">`Always` - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="4d51b-107">`Never` -Ciò impedisce l'utilizzo WebSockets.</span><span class="sxs-lookup"><span data-stu-id="4d51b-107">`Never` - This prevents WebSockets from being used.</span></span> <span data-ttu-id="4d51b-108">Il tentativo di utilizzo di un contratto duplex con questa impostazione genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d51b-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="4d51b-109">`WhenDuplex` -Questo è il valore predefinito e si comporta come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4d51b-109">`WhenDuplex` - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="4d51b-110"><xref:System.ServiceModel.NetHttpBinding> supporta sessioni affidabili sia in modalità HTTP sia in modalità WebSocket.</span><span class="sxs-lookup"><span data-stu-id="4d51b-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="4d51b-111">Nella modalità WebSocket, le sessioni vengono fornite dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="4d51b-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4d51b-112">Quando si usa <xref:System.ServiceModel.NetHttpBinding> e l'elemento TransferMode dell'associazione è impostato su TransferMode.Streamed, i flussi di grandi dimensioni possono causare un deadlock e quindi il timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d51b-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="4d51b-113">Per risolvere il problema inviare messaggi più piccoli o usare TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="4d51b-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="4d51b-114">Configurazione dell'utilizzo di NetHttpBinding in un servizio</span><span class="sxs-lookup"><span data-stu-id="4d51b-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="4d51b-115">L'endpoint <xref:System.ServiceModel.NetHttpBinding> può essere configurato come qualsiasi altra associazione.</span><span class="sxs-lookup"><span data-stu-id="4d51b-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="4d51b-116">Nel frammento di configurazione seguente è illustrato come configurare un servizio WCF con <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4d51b-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 <span data-ttu-id="4d51b-117">Nel frammento di codice seguente viene illustrato come aggiungere l'oggetto <xref:System.ServiceModel.NetHttpBinding> nel codice.</span><span class="sxs-lookup"><span data-stu-id="4d51b-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d51b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d51b-118">See Also</span></span>  
 [<span data-ttu-id="4d51b-119">Configurazione delle associazioni per i servizi</span><span class="sxs-lookup"><span data-stu-id="4d51b-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="4d51b-120">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4d51b-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="4d51b-121">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="4d51b-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="4d51b-122">Servizi duplex</span><span class="sxs-lookup"><span data-stu-id="4d51b-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
