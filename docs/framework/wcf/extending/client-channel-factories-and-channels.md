---
title: 'Client: channel factory e canali'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4a841fec01b3a0ef29cd836cccf3f337f29ddb6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="client-channel-factories-and-channels"></a><span data-ttu-id="3fa44-102">Client: channel factory e canali</span><span class="sxs-lookup"><span data-stu-id="3fa44-102">Client: Channel Factories and Channels</span></span>
<span data-ttu-id="3fa44-103">In questo argomento viene illustrata la creazione di channel factory e canali.</span><span class="sxs-lookup"><span data-stu-id="3fa44-103">This topic discusses the creation of channel factories and channels.</span></span>  
  
## <a name="channel-factories-and-channels"></a><span data-ttu-id="3fa44-104">Channel factory e canali</span><span class="sxs-lookup"><span data-stu-id="3fa44-104">Channel Factories and Channels</span></span>  
 <span data-ttu-id="3fa44-105">Le channel factory sono responsabili della creazione di canali.</span><span class="sxs-lookup"><span data-stu-id="3fa44-105">Channel factories are responsible for creating channels.</span></span> <span data-ttu-id="3fa44-106">I canali creati da channel factory vengono usati per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3fa44-106">Channels created by channel factories are used for sending messages.</span></span> <span data-ttu-id="3fa44-107">Questi canali ottengono il messaggio dal livello superiore, eseguono l'elaborazione necessaria, quindi inviano il messaggio al livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="3fa44-107">These channels are responsible for getting the message from the layer above, performing whatever processing is necessary, then sending the message to the layer below.</span></span> <span data-ttu-id="3fa44-108">Nel grafico seguente viene illustrato questo processo.</span><span class="sxs-lookup"><span data-stu-id="3fa44-108">The following graphic illustrates this process.</span></span>  
  
 <span data-ttu-id="3fa44-109">![Factory client e i canali](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span><span class="sxs-lookup"><span data-stu-id="3fa44-109">![Client Factories and Channels](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span></span>  
<span data-ttu-id="3fa44-110">Una channel factory crea canali.</span><span class="sxs-lookup"><span data-stu-id="3fa44-110">A channel factory creates channels.</span></span>  
  
 <span data-ttu-id="3fa44-111">Quando sono chiuse, le channel factory sono responsabili della chiusura di tutti i canali creati non ancora chiusi.</span><span class="sxs-lookup"><span data-stu-id="3fa44-111">When closed, channel factories are responsible for closing any channels they created that are not yet closed.</span></span> <span data-ttu-id="3fa44-112">Il modello rappresentato è asimmetrico perché quando un listener del canale viene chiuso, smette solo di accettare nuovi canali, mentre lascia aperti i canali esistenti affinché possano continuare a ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="3fa44-112">Note that the model is asymmetric here because when a channel listener is closed, it only stops accepting new channels but leaves existing channels open so that they can continue receiving messages.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="3fa44-113"> fornisce supporti di classi di base per questo processo.</span><span class="sxs-lookup"><span data-stu-id="3fa44-113"> provides base class helpers for this process.</span></span> <span data-ttu-id="3fa44-114">(Per un diagramma di classi di supporto canale descritti in questo argomento, vedere [Cenni preliminari sul modello di canale](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="3fa44-114">(For a diagram of the channel helper classes discussed in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span></span>  
  
-   <span data-ttu-id="3fa44-115">Il <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> e impone la macchina a stati descritta nel passaggio 2 di [sviluppo canali](../../../../docs/framework/wcf/extending/developing-channels.md).</span><span class="sxs-lookup"><span data-stu-id="3fa44-115">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
-   <span data-ttu-id="3fa44-116">Il '<xref:System.ServiceModel.Channels.ChannelManagerBase> implementa <xref:System.ServiceModel.Channels.CommunicationObject> e fornisce una classe di base unificata per <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> e <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-116">The``<xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> and <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3fa44-117">La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-117">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
-   <span data-ttu-id="3fa44-118">Il '<xref:System.ServiceModel.Channels.ChannelFactoryBase> implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> e <xref:System.ServiceModel.Channels.IChannelFactory> e li consolida il `CreateChannel` overload in uno `OnCreateChannel` metodo astratto.</span><span class="sxs-lookup"><span data-stu-id="3fa44-118">The``<xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
-   <span data-ttu-id="3fa44-119">Il '<xref:System.ServiceModel.Channels.ChannelListenerBase> implementa <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-119">The``<xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="3fa44-120">Si occupa della gestione dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="3fa44-120">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="3fa44-121">La seguente discussione si basa il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="3fa44-121">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="creating-a-channel-factory"></a><span data-ttu-id="3fa44-122">Creazione di una channel factory</span><span class="sxs-lookup"><span data-stu-id="3fa44-122">Creating a Channel Factory</span></span>  
 <span data-ttu-id="3fa44-123">`UdpChannelFactory` deriva da <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-123">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="3fa44-124">L'esempio esegue l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> per fornire accesso alla versione del messaggio del codificatore di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3fa44-124">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="3fa44-125">L'esempio esegue inoltre l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> per chiudere l'istanza di <xref:System.ServiceModel.Channels.BufferManager> quando la macchina a stati esegue la transizione.</span><span class="sxs-lookup"><span data-stu-id="3fa44-125">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> to tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="3fa44-126">Canale di output UDP</span><span class="sxs-lookup"><span data-stu-id="3fa44-126">The UDP Output Channel</span></span>  
 <span data-ttu-id="3fa44-127">`UdpOutputChannel` implementa <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-127">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="3fa44-128">Il costruttore convalida gli argomenti e costruisce un oggetto <xref:System.Net.EndPoint> di destinazione basato sull'elemento <xref:System.ServiceModel.EndpointAddress> che viene passato.</span><span class="sxs-lookup"><span data-stu-id="3fa44-128">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
 <span data-ttu-id="3fa44-129">L'override di <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> crea un socket che viene usato per inviare messaggi a questa classe <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="3fa44-129">The override of <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> creates a socket that is used to send messages to this <xref:System.Net.EndPoint>.</span></span>  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 <span data-ttu-id="3fa44-130">Il canale può essere chiuso normalmente o in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="3fa44-130">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="3fa44-131">Se il canale viene chiuso normalmente, il socket viene chiuso e viene eseguita una chiamata al metodo `OnClose` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="3fa44-131">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="3fa44-132">Se viene generata un'eccezione, l'infrastruttura chiama `Abort` per verificare che il canale sia pulito.</span><span class="sxs-lookup"><span data-stu-id="3fa44-132">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 <span data-ttu-id="3fa44-133">Implementare `Send()` e `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="3fa44-133">Implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="3fa44-134">In questo modo si ottengono due sezioni principali.</span><span class="sxs-lookup"><span data-stu-id="3fa44-134">This breaks down into two main sections.</span></span> <span data-ttu-id="3fa44-135">Prima serializzare il messaggio in una matrice di byte:</span><span class="sxs-lookup"><span data-stu-id="3fa44-135">First serialize the message into a byte array:</span></span>  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="3fa44-136">Inviare quindi i dati risultanti sulla rete.</span><span class="sxs-lookup"><span data-stu-id="3fa44-136">Then send the resulting data on the wire:</span></span>  
  
```  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fa44-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa44-137">See Also</span></span>  
 [<span data-ttu-id="3fa44-138">Sviluppo di canali</span><span class="sxs-lookup"><span data-stu-id="3fa44-138">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)
