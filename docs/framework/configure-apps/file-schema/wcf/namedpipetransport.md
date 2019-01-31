---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e30fcd5952fadc3b6cf30cb352a3bb51c86cc117
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285910"
---
# <a name="namedpipetransport"></a><span data-ttu-id="89b3a-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="89b3a-101">\<namedPipeTransport></span></span>
<span data-ttu-id="89b3a-102">Definisce un trasporto che induce un canale a trasferire messaggi usando named pipe quando è incluso in un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="89b3a-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="89b3a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="89b3a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="89b3a-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="89b3a-104">\<bindings></span></span>  
<span data-ttu-id="89b3a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="89b3a-105">\<customBinding></span></span>  
<span data-ttu-id="89b3a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="89b3a-106">\<binding></span></span>  
<span data-ttu-id="89b3a-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="89b3a-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b3a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89b3a-108">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b3a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89b3a-109">Attributes and Elements</span></span>  
<span data-ttu-id="89b3a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89b3a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b3a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="89b3a-111">Attributes</span></span>  
<span data-ttu-id="89b3a-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="89b3a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89b3a-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89b3a-113">Child Elements</span></span>  
  
|<span data-ttu-id="89b3a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="89b3a-114">Element</span></span>|<span data-ttu-id="89b3a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89b3a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89b3a-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="89b3a-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="89b3a-117">Ottiene o imposta un <xref:System.TimeSpan> che determina il tempo massimo di un canale può trovarsi nello stato di inizializzazione prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="89b3a-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="89b3a-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="89b3a-118">ConnectionBufferSize</span></span>|<span data-ttu-id="89b3a-119">Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.</span><span class="sxs-lookup"><span data-stu-id="89b3a-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="89b3a-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="89b3a-120">hostNameComparisonMode</span></span>|<span data-ttu-id="89b3a-121">Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.</span><span class="sxs-lookup"><span data-stu-id="89b3a-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="89b3a-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="89b3a-122">manualAddressing</span></span>|<span data-ttu-id="89b3a-123">Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="89b3a-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="89b3a-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="89b3a-124">maxBufferPoolSize</span></span>|<span data-ttu-id="89b3a-125">Ottiene o imposta la dimensione massima, in byte, del pool di buffer utilizzati dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="89b3a-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="89b3a-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="89b3a-126">maxBufferSize</span></span>|<span data-ttu-id="89b3a-127">Ottiene o imposta la dimensione massima del buffer da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="89b3a-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="89b3a-128">Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.</span><span class="sxs-lookup"><span data-stu-id="89b3a-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="89b3a-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="89b3a-129">maxOutputDelay</span></span>|<span data-ttu-id="89b3a-130">Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.</span><span class="sxs-lookup"><span data-stu-id="89b3a-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="89b3a-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="89b3a-131">maxPendingAccepts</span></span>|<span data-ttu-id="89b3a-132">Ottiene o imposta il numero massimo di canali di che un servizio può avere in attesa di un listener per l'elaborazione delle connessioni in ingresso al servizio.</span><span class="sxs-lookup"><span data-stu-id="89b3a-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="89b3a-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="89b3a-133">maxPendingConnections</span></span>|<span data-ttu-id="89b3a-134">Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="89b3a-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="89b3a-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="89b3a-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="89b3a-136">Ottiene e imposta la dimensione massima consentita del messaggio, in byte, che possono essere ricevuti.</span><span class="sxs-lookup"><span data-stu-id="89b3a-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="89b3a-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="89b3a-137">transferMode</span></span>|<span data-ttu-id="89b3a-138">Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.</span><span class="sxs-lookup"><span data-stu-id="89b3a-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="89b3a-139">\<connectionPoolSettings > di \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="89b3a-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="89b3a-140">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="89b3a-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89b3a-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89b3a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="89b3a-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="89b3a-142">Element</span></span>|<span data-ttu-id="89b3a-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89b3a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b3a-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="89b3a-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="89b3a-145">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="89b3a-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b3a-146">Note</span><span class="sxs-lookup"><span data-stu-id="89b3a-146">Remarks</span></span>  
<span data-ttu-id="89b3a-147">Questo trasporto usa URI nel formato "net.pipe://nomehost/percorso".</span><span class="sxs-lookup"><span data-stu-id="89b3a-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="89b3a-148">Gli altri componenti URI sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="89b3a-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="89b3a-149">L'elemento `namedPipeTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto delle named pipe.</span><span class="sxs-lookup"><span data-stu-id="89b3a-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="89b3a-150">Questo trasporto viene usato per la comunicazione da computer con Windows Communication Foundation (WCF) a WCF.</span><span class="sxs-lookup"><span data-stu-id="89b3a-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b3a-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89b3a-151">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="89b3a-152">Trasporti</span><span class="sxs-lookup"><span data-stu-id="89b3a-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="89b3a-153">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="89b3a-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="89b3a-154">Associazioni</span><span class="sxs-lookup"><span data-stu-id="89b3a-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="89b3a-155">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="89b3a-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="89b3a-156">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="89b3a-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="89b3a-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="89b3a-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
