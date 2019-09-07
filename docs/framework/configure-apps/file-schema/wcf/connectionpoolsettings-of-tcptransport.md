---
title: <connectionPoolSettings> di <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398102"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="b83c2-102">\<> connectionPoolSettings di \<TcpTransport ></span><span class="sxs-lookup"><span data-stu-id="b83c2-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="b83c2-103">Specifica impostazioni aggiuntive del pool di connessioni per un trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="b83c2-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="b83c2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b83c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b83c2-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b83c2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b83c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b83c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b83c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b83c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b83c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="b83c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b83c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> tcpTransport**](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="b83c2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="b83c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> connectionPoolSettings**</span><span class="sxs-lookup"><span data-stu-id="b83c2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b83c2-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b83c2-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b83c2-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b83c2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b83c2-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b83c2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b83c2-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="b83c2-114">Attributes</span></span>  
  
|<span data-ttu-id="b83c2-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="b83c2-115">Attribute</span></span>|<span data-ttu-id="b83c2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b83c2-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="b83c2-117">Stringa che definisce il nome del pool di connessioni usato per canali in uscita.</span><span class="sxs-lookup"><span data-stu-id="b83c2-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="b83c2-118">In modalità di invio nel flusso, le connessioni non sono condivise, pertanto il pool di connessioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b83c2-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="b83c2-119">Il valore predefinito è una stringa "default".</span><span class="sxs-lookup"><span data-stu-id="b83c2-119">The default is a "default" string.</span></span> <span data-ttu-id="b83c2-120">È possibile modificare questo valore per isolare le connessioni per un particolare client in gruppi separati.</span><span class="sxs-lookup"><span data-stu-id="b83c2-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="b83c2-121">Elemento <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="b83c2-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="b83c2-122">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="b83c2-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="b83c2-123"><xref:System.TimeSpan> specifica il periodo di tempo dopo il quale una connessione attiva viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="b83c2-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="b83c2-124">L'impostazione predefinita è 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="b83c2-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="b83c2-125">Una connessione viene chiusa dopo che è stata restituita alla cache di connessione e non durante la trasmissione attiva.</span><span class="sxs-lookup"><span data-stu-id="b83c2-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="b83c2-126">La cache della connessione usata dal trasporto TCP crea nuove connessioni in base a ogni endpoint, fino al limite della cache impostato da `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="b83c2-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="b83c2-127">Numero intero positivo che specifica il numero massimo di connessioni a un endpoint remoto iniziate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b83c2-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="b83c2-128">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="b83c2-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="b83c2-129">`idleTimeout` limita il periodo di tempo entro il quale le connessioni rimangono in coda prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b83c2-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="b83c2-130">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="b83c2-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="b83c2-131">Questo attributo limita il numero di connessioni attive simultanee dal client a un particolare endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="b83c2-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="b83c2-132">Se questo valore viene superato a causa di un numero maggiore di connessioni client attive, può risultare che il servizio non risponda al client.</span><span class="sxs-lookup"><span data-stu-id="b83c2-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="b83c2-133">In questo caso, il valore deve essere regolato in modo da superare il numero massimo di connessioni client simultanee previste a un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="b83c2-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b83c2-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b83c2-134">Child Elements</span></span>  
 <span data-ttu-id="b83c2-135">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b83c2-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b83c2-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b83c2-136">Parent Elements</span></span>  
  
|<span data-ttu-id="b83c2-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="b83c2-137">Element</span></span>|<span data-ttu-id="b83c2-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b83c2-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b83c2-139">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="b83c2-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="b83c2-140">Definisce un trasporto che fa in modo che un canale trasferisca messaggi usando named pipe.</span><span class="sxs-lookup"><span data-stu-id="b83c2-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b83c2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b83c2-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b83c2-142">Trasporti</span><span class="sxs-lookup"><span data-stu-id="b83c2-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b83c2-143">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="b83c2-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b83c2-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b83c2-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b83c2-145">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b83c2-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b83c2-146">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b83c2-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b83c2-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b83c2-147">\<customBinding></span></span>](custombinding.md)
