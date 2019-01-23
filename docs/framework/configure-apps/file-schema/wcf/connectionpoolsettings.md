---
title: '&lt;connectionPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 1e3001f60ae0f18fee88678cae1e9e55d90822c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526764"
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="ea980-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="ea980-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="ea980-103">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="ea980-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="ea980-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ea980-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ea980-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ea980-105">\<bindings></span></span>  
<span data-ttu-id="ea980-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea980-106">\<customBinding></span></span>  
<span data-ttu-id="ea980-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea980-107">\<binding></span></span>  
<span data-ttu-id="ea980-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="ea980-108">\<namePipeTransport></span></span>  
<span data-ttu-id="ea980-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="ea980-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea980-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea980-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea980-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea980-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ea980-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea980-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea980-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea980-113">Attributes</span></span>  
  
|<span data-ttu-id="ea980-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ea980-114">Attribute</span></span>|<span data-ttu-id="ea980-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea980-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="ea980-116">Stringa che definisce il nome del pool di connessioni usato per canali in uscita.</span><span class="sxs-lookup"><span data-stu-id="ea980-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="ea980-117">In modalità di invio nel flusso, le connessioni non sono condivise, pertanto il pool di connessioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ea980-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="ea980-118">Il valore predefinito è una stringa "default".</span><span class="sxs-lookup"><span data-stu-id="ea980-118">The default is a "default" string.</span></span> <span data-ttu-id="ea980-119">È possibile modificare questo valore per isolare le connessioni per un particolare client in gruppi separati.</span><span class="sxs-lookup"><span data-stu-id="ea980-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="ea980-120">Elemento <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="ea980-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="ea980-121">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="ea980-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="ea980-122">Numero intero positivo che specifica il numero massimo di connessioni a un endpoint remoto iniziate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ea980-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="ea980-123">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="ea980-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="ea980-124">`idleTimeout` limita il periodo di tempo entro il quale le connessioni rimangono in coda prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ea980-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="ea980-125">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="ea980-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="ea980-126">Questo attributo limita il numero di connessioni attive simultanee dal client a un particolare endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="ea980-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="ea980-127">Se questo valore viene superato a causa di un numero maggiore di connessioni client attive, può risultare che il servizio non risponda al client.</span><span class="sxs-lookup"><span data-stu-id="ea980-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="ea980-128">In questo caso, il valore deve essere regolato in modo da superare il numero massimo di connessioni client simultanee previste a un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="ea980-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea980-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea980-129">Child Elements</span></span>  
 <span data-ttu-id="ea980-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ea980-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea980-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea980-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ea980-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea980-132">Element</span></span>|<span data-ttu-id="ea980-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea980-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea980-134">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="ea980-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="ea980-135">Definisce un trasporto che fa in modo che un canale trasferisca messaggi usando named pipe.</span><span class="sxs-lookup"><span data-stu-id="ea980-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea980-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea980-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ea980-137">Trasporti</span><span class="sxs-lookup"><span data-stu-id="ea980-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="ea980-138">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="ea980-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ea980-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ea980-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ea980-140">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ea980-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ea980-141">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ea980-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ea980-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea980-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
