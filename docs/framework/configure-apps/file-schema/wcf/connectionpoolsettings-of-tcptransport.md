---
title: '&lt;connectionPoolSettings&gt; di &lt;tcpTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61e4036ef5fe4731316aabeed2e3208422894194
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltconnectionpoolsettingsgt-of-lttcptransportgt"></a><span data-ttu-id="cbced-102">&lt;connectionPoolSettings&gt; di &lt;tcpTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="cbced-102">&lt;connectionPoolSettings&gt; of &lt;tcpTransport&gt;</span></span>
<span data-ttu-id="cbced-103">Specifica impostazioni aggiuntive del pool di connessioni per un trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="cbced-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="cbced-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cbced-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cbced-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="cbced-105">\<bindings></span></span>  
<span data-ttu-id="cbced-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cbced-106">\<customBinding></span></span>  
<span data-ttu-id="cbced-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cbced-107">\<binding></span></span>  
<span data-ttu-id="cbced-108">\<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="cbced-108">\<tcpTransport></span></span>  
<span data-ttu-id="cbced-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="cbced-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbced-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbced-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
    groupName="String"  
    idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbced-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cbced-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cbced-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cbced-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbced-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="cbced-113">Attributes</span></span>  
  
|<span data-ttu-id="cbced-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="cbced-114">Attribute</span></span>|<span data-ttu-id="cbced-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbced-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="cbced-116">Stringa che definisce il nome del pool di connessioni usato per canali in uscita.</span><span class="sxs-lookup"><span data-stu-id="cbced-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="cbced-117">In modalità di invio nel flusso, le connessioni non sono condivise, pertanto il pool di connessioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="cbced-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="cbced-118">Il valore predefinito è una stringa "default".</span><span class="sxs-lookup"><span data-stu-id="cbced-118">The default is a "default" string.</span></span> <span data-ttu-id="cbced-119">È possibile modificare questo valore per isolare le connessioni per un particolare client in gruppi separati.</span><span class="sxs-lookup"><span data-stu-id="cbced-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="cbced-120">Elemento <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="cbced-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="cbced-121">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="cbced-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="cbced-122"><xref:System.TimeSpan> specifica il periodo di tempo dopo il quale una connessione attiva viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="cbced-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="cbced-123">L'impostazione predefinita è 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="cbced-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="cbced-124">Una connessione viene chiusa dopo che è stata restituita alla cache di connessione e non durante la trasmissione attiva.</span><span class="sxs-lookup"><span data-stu-id="cbced-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="cbced-125">La cache della connessione usata dal trasporto TCP crea nuove connessioni in base a ogni endpoint, fino al limite della cache impostato da `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="cbced-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="cbced-126">Numero intero positivo che specifica il numero massimo di connessioni a un endpoint remoto iniziate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="cbced-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="cbced-127">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="cbced-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="cbced-128">`idleTimeout` limita il periodo di tempo entro il quale le connessioni rimangono in coda prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cbced-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="cbced-129">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="cbced-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="cbced-130">Questo attributo limita il numero di connessioni attive simultanee dal client a un particolare endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="cbced-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="cbced-131">Se questo valore viene superato a causa di un numero maggiore di connessioni client attive, può risultare che il servizio non risponda al client.</span><span class="sxs-lookup"><span data-stu-id="cbced-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="cbced-132">In questo caso, il valore deve essere regolato in modo da superare il numero massimo di connessioni client simultanee previste a un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="cbced-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cbced-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cbced-133">Child Elements</span></span>  
 <span data-ttu-id="cbced-134">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cbced-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cbced-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cbced-135">Parent Elements</span></span>  
  
|<span data-ttu-id="cbced-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="cbced-136">Element</span></span>|<span data-ttu-id="cbced-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbced-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbced-138">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="cbced-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="cbced-139">Definisce un trasporto che fa in modo che un canale trasferisca messaggi usando named pipe.</span><span class="sxs-lookup"><span data-stu-id="cbced-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbced-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbced-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="cbced-141">Trasporti</span><span class="sxs-lookup"><span data-stu-id="cbced-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="cbced-142">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="cbced-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="cbced-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cbced-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cbced-144">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="cbced-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="cbced-145">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cbced-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="cbced-146">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cbced-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
