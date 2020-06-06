---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736581"
---
# \<namedPipeTransport>
<span data-ttu-id="2db76-101">Definisce un trasporto che induce un canale a trasferire messaggi usando named pipe quando è incluso in un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2db76-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="2db76-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2db76-102">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2db76-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2db76-103">Attributes and Elements</span></span>  
<span data-ttu-id="2db76-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2db76-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2db76-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="2db76-105">Attributes</span></span>  
<span data-ttu-id="2db76-106">No.</span><span class="sxs-lookup"><span data-stu-id="2db76-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2db76-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2db76-107">Child Elements</span></span>  
  
|<span data-ttu-id="2db76-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="2db76-108">Element</span></span>|<span data-ttu-id="2db76-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2db76-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2db76-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="2db76-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="2db76-111">Ottiene o imposta un <xref:System.TimeSpan> che determina il periodo massimo di tempo entro il quale il canale può trovarsi nello stato di inizializzazione prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="2db76-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="2db76-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="2db76-112">ConnectionBufferSize</span></span>|<span data-ttu-id="2db76-113">Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.</span><span class="sxs-lookup"><span data-stu-id="2db76-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="2db76-114">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="2db76-114">hostNameComparisonMode</span></span>|<span data-ttu-id="2db76-115">Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.</span><span class="sxs-lookup"><span data-stu-id="2db76-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="2db76-116">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="2db76-116">manualAddressing</span></span>|<span data-ttu-id="2db76-117">Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2db76-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="2db76-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="2db76-118">maxBufferPoolSize</span></span>|<span data-ttu-id="2db76-119">Ottiene o imposta le dimensioni massime in byte di qualsiasi pool di buffer utilizzato dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="2db76-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="2db76-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="2db76-120">maxBufferSize</span></span>|<span data-ttu-id="2db76-121">Ottiene o imposta la dimensione massima del buffer da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2db76-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="2db76-122">Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.</span><span class="sxs-lookup"><span data-stu-id="2db76-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="2db76-123">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="2db76-123">maxOutputDelay</span></span>|<span data-ttu-id="2db76-124">Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.</span><span class="sxs-lookup"><span data-stu-id="2db76-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="2db76-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="2db76-125">maxPendingAccepts</span></span>|<span data-ttu-id="2db76-126">Ottiene o imposta il numero massimo di canali che possono attendere nel listener di un servizio per l'elaborazione delle connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="2db76-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="2db76-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="2db76-127">maxPendingConnections</span></span>|<span data-ttu-id="2db76-128">Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="2db76-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="2db76-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="2db76-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="2db76-130">Ottiene e imposta la dimensione massima consentita del messaggio, in byte, che può essere ricevuta.</span><span class="sxs-lookup"><span data-stu-id="2db76-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="2db76-131">transferMode</span><span class="sxs-lookup"><span data-stu-id="2db76-131">transferMode</span></span>|<span data-ttu-id="2db76-132">Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.</span><span class="sxs-lookup"><span data-stu-id="2db76-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="2db76-133">\<connectionPoolSettings>di\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="2db76-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="2db76-134">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="2db76-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2db76-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2db76-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2db76-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="2db76-136">Element</span></span>|<span data-ttu-id="2db76-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2db76-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2db76-138">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2db76-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2db76-139">Commenti</span><span class="sxs-lookup"><span data-stu-id="2db76-139">Remarks</span></span>  
<span data-ttu-id="2db76-140">Questo trasporto usa URI nel formato "net.pipe://nomehost/percorso".</span><span class="sxs-lookup"><span data-stu-id="2db76-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="2db76-141">Gli altri componenti URI sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="2db76-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="2db76-142">L'elemento `namedPipeTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto delle named pipe.</span><span class="sxs-lookup"><span data-stu-id="2db76-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="2db76-143">Questo trasporto viene usato per la comunicazione da computer con Windows Communication Foundation (WCF) a WCF.</span><span class="sxs-lookup"><span data-stu-id="2db76-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db76-144">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2db76-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2db76-145">Trasporti</span><span class="sxs-lookup"><span data-stu-id="2db76-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="2db76-146">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="2db76-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="2db76-147">Binding</span><span class="sxs-lookup"><span data-stu-id="2db76-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2db76-148">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="2db76-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2db76-149">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2db76-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
