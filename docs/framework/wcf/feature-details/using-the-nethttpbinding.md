---
title: Uso di NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: ac6fc658731d032051f2dfd4058397f9b9a55828
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585636"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="bb609-102">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="bb609-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="bb609-103"><xref:System.ServiceModel.NetHttpBinding> è un'associazione progettata per usare i servizi HTTP o WebSocket e usa la codifica binaria per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb609-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="bb609-104">L'oggetto <xref:System.ServiceModel.NetHttpBinding> rileverà se viene usato con un contratto request/reply o un contratto duplex e modificherà il comportamento di conseguenza. Utilizzerà HTTP per i contratti request/reply e WebSockets per i contratti duplex.</span><span class="sxs-lookup"><span data-stu-id="bb609-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="bb609-105">È possibile eseguire l'override di questo comportamento usando l'impostazione <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:</span><span class="sxs-lookup"><span data-stu-id="bb609-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="bb609-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always>-Impone l'uso di WebSocket anche per i contratti request/reply.</span><span class="sxs-lookup"><span data-stu-id="bb609-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="bb609-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never>-Ciò impedisce l'uso di WebSocket.</span><span class="sxs-lookup"><span data-stu-id="bb609-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> - This prevents WebSockets from being used.</span></span> <span data-ttu-id="bb609-108">Il tentativo di utilizzo di un contratto duplex con questa impostazione genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bb609-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="bb609-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex>-Si tratta del valore predefinito e si comporta come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bb609-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="bb609-110"><xref:System.ServiceModel.NetHttpBinding> supporta sessioni affidabili sia in modalità HTTP sia in modalità WebSocket.</span><span class="sxs-lookup"><span data-stu-id="bb609-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="bb609-111">Nella modalità WebSocket, le sessioni vengono fornite dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="bb609-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="bb609-112">Quando si usa <xref:System.ServiceModel.NetHttpBinding> e l'elemento TransferMode dell'associazione è impostato su TransferMode.Streamed, i flussi di grandi dimensioni possono causare un deadlock e quindi il timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb609-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="bb609-113">Per risolvere il problema inviare messaggi più piccoli o usare TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="bb609-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="bb609-114">Configurazione dell'utilizzo di NetHttpBinding in un servizio</span><span class="sxs-lookup"><span data-stu-id="bb609-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="bb609-115">L'endpoint <xref:System.ServiceModel.NetHttpBinding> può essere configurato come qualsiasi altra associazione.</span><span class="sxs-lookup"><span data-stu-id="bb609-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="bb609-116">Nel frammento di configurazione seguente è illustrato come configurare un servizio WCF con <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="bb609-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
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
    ...
  </system.serviceModel>  
```  
  
 <span data-ttu-id="bb609-117">Nel frammento di codice seguente viene illustrato come aggiungere l'oggetto <xref:System.ServiceModel.NetHttpBinding> nel codice.</span><span class="sxs-lookup"><span data-stu-id="bb609-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb609-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb609-118">See also</span></span>

- [<span data-ttu-id="bb609-119">Configurazione di associazioni per servizi</span><span class="sxs-lookup"><span data-stu-id="bb609-119">Configuring Bindings for Services</span></span>](../configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="bb609-120">Binding</span><span class="sxs-lookup"><span data-stu-id="bb609-120">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="bb609-121">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="bb609-121">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="bb609-122">Servizi duplex</span><span class="sxs-lookup"><span data-stu-id="bb609-122">Duplex Services</span></span>](duplex-services.md)
