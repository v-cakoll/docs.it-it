---
title: 'Client: Channel factory e canali'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: bfa5d2478d5c12f16c2d9531de02e1c868eab560
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858410"
---
# <a name="client-channel-factories-and-channels"></a><span data-ttu-id="feb5e-102">Client: Channel factory e canali</span><span class="sxs-lookup"><span data-stu-id="feb5e-102">Client: Channel Factories and Channels</span></span>
<span data-ttu-id="feb5e-103">In questo argomento viene illustrata la creazione di channel factory e canali.</span><span class="sxs-lookup"><span data-stu-id="feb5e-103">This topic discusses the creation of channel factories and channels.</span></span>  
  
## <a name="channel-factories-and-channels"></a><span data-ttu-id="feb5e-104">Channel factory e canali</span><span class="sxs-lookup"><span data-stu-id="feb5e-104">Channel Factories and Channels</span></span>  
 <span data-ttu-id="feb5e-105">Le channel factory sono responsabili della creazione di canali.</span><span class="sxs-lookup"><span data-stu-id="feb5e-105">Channel factories are responsible for creating channels.</span></span> <span data-ttu-id="feb5e-106">I canali creati da channel factory vengono usati per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="feb5e-106">Channels created by channel factories are used for sending messages.</span></span> <span data-ttu-id="feb5e-107">Questi canali ottengono il messaggio dal livello superiore, eseguono l'elaborazione necessaria, quindi inviano il messaggio al livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="feb5e-107">These channels are responsible for getting the message from the layer above, performing whatever processing is necessary, then sending the message to the layer below.</span></span> <span data-ttu-id="feb5e-108">Nel grafico seguente viene illustrato questo processo.</span><span class="sxs-lookup"><span data-stu-id="feb5e-108">The following graphic illustrates this process.</span></span>  
  
 <span data-ttu-id="feb5e-109">![Factory di client e canali](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span><span class="sxs-lookup"><span data-stu-id="feb5e-109">![Client Factories and Channels](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span></span>  
<span data-ttu-id="feb5e-110">Una channel factory crea canali.</span><span class="sxs-lookup"><span data-stu-id="feb5e-110">A channel factory creates channels.</span></span>  
  
 <span data-ttu-id="feb5e-111">Quando sono chiuse, le channel factory sono responsabili della chiusura di tutti i canali creati non ancora chiusi.</span><span class="sxs-lookup"><span data-stu-id="feb5e-111">When closed, channel factories are responsible for closing any channels they created that are not yet closed.</span></span> <span data-ttu-id="feb5e-112">Il modello rappresentato è asimmetrico perché quando un listener del canale viene chiuso, smette solo di accettare nuovi canali, mentre lascia aperti i canali esistenti affinché possano continuare a ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="feb5e-112">Note that the model is asymmetric here because when a channel listener is closed, it only stops accepting new channels but leaves existing channels open so that they can continue receiving messages.</span></span>  
  
 <span data-ttu-id="feb5e-113">WCF fornisce gli helper di classe di base per questo processo.</span><span class="sxs-lookup"><span data-stu-id="feb5e-113">WCF provides base class helpers for this process.</span></span> <span data-ttu-id="feb5e-114">(Per un diagramma delle classi di supporto del canale descritti in questo argomento, vedere [Cenni preliminari sul modello di canale](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="feb5e-114">(For a diagram of the channel helper classes discussed in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span></span>  
  
-   <span data-ttu-id="feb5e-115">Il <xref:System.ServiceModel.Channels.CommunicationObject> classe implementa <xref:System.ServiceModel.ICommunicationObject> e applica la macchina a stati descritta nel passaggio 2 della [emergenti canali](../../../../docs/framework/wcf/extending/developing-channels.md).</span><span class="sxs-lookup"><span data-stu-id="feb5e-115">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
-   <span data-ttu-id="feb5e-116">Il <xref:System.ServiceModel.Channels.ChannelManagerBase> classe implementa <xref:System.ServiceModel.Channels.CommunicationObject> e fornisce una classe di base unificata per <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> e <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-116">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> and <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="feb5e-117">La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-117">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>
  
-   <span data-ttu-id="feb5e-118">Il <xref:System.ServiceModel.Channels.ChannelFactoryBase> classe implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> e <xref:System.ServiceModel.Channels.IChannelFactory> e consolida il `CreateChannel` overload in un unico `OnCreateChannel` metodo astratto.</span><span class="sxs-lookup"><span data-stu-id="feb5e-118">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>
  
-   <span data-ttu-id="feb5e-119">Il <xref:System.ServiceModel.Channels.ChannelListenerBase> classe implementa <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-119">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="feb5e-120">Si occupa della gestione dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="feb5e-120">It takes care of basic state management.</span></span> 
  
 <span data-ttu-id="feb5e-121">La discussione seguente si basa il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="feb5e-121">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="creating-a-channel-factory"></a><span data-ttu-id="feb5e-122">Creazione di una channel factory</span><span class="sxs-lookup"><span data-stu-id="feb5e-122">Creating a Channel Factory</span></span>  
 <span data-ttu-id="feb5e-123">`UdpChannelFactory` deriva da <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-123">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="feb5e-124">L'esempio esegue l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> per fornire accesso alla versione del messaggio del codificatore di messaggi.</span><span class="sxs-lookup"><span data-stu-id="feb5e-124">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="feb5e-125">L'esempio esegue inoltre l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> per chiudere l'istanza di <xref:System.ServiceModel.Channels.BufferManager> quando la macchina a stati esegue la transizione.</span><span class="sxs-lookup"><span data-stu-id="feb5e-125">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> to tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="feb5e-126">Canale di output UDP</span><span class="sxs-lookup"><span data-stu-id="feb5e-126">The UDP Output Channel</span></span>  
 <span data-ttu-id="feb5e-127">`UdpOutputChannel` implementa <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-127">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="feb5e-128">Il costruttore convalida gli argomenti e costruisce un oggetto <xref:System.Net.EndPoint> di destinazione basato sull'elemento <xref:System.ServiceModel.EndpointAddress> che viene passato.</span><span class="sxs-lookup"><span data-stu-id="feb5e-128">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
 <span data-ttu-id="feb5e-129">L'override di <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> crea un socket che viene usato per inviare messaggi a questa classe <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="feb5e-129">The override of <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> creates a socket that is used to send messages to this <xref:System.Net.EndPoint>.</span></span>  
  
 ```csharp 
this.socket = new Socket(  
this.remoteEndPoint.AddressFamily,
   SocketType.Dgram,
   ProtocolType.Udp
);  
```  

 <span data-ttu-id="feb5e-130">Il canale può essere chiuso normalmente o in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="feb5e-130">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="feb5e-131">Se il canale viene chiuso normalmente, il socket viene chiuso e viene eseguita una chiamata al metodo `OnClose` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="feb5e-131">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="feb5e-132">Se viene generata un'eccezione, l'infrastruttura chiama `Abort` per verificare che il canale sia pulito.</span><span class="sxs-lookup"><span data-stu-id="feb5e-132">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 <span data-ttu-id="feb5e-133">Implementare `Send()` e `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="feb5e-133">Implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="feb5e-134">In questo modo si ottengono due sezioni principali.</span><span class="sxs-lookup"><span data-stu-id="feb5e-134">This breaks down into two main sections.</span></span> <span data-ttu-id="feb5e-135">Prima serializzare il messaggio in una matrice di byte:</span><span class="sxs-lookup"><span data-stu-id="feb5e-135">First serialize the message into a byte array:</span></span>  
  
```csharp  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="feb5e-136">Inviare quindi i dati risultanti sulla rete.</span><span class="sxs-lookup"><span data-stu-id="feb5e-136">Then send the resulting data on the wire:</span></span>  
  
```csharp  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="feb5e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="feb5e-137">See also</span></span>

- [<span data-ttu-id="feb5e-138">Sviluppo di canali</span><span class="sxs-lookup"><span data-stu-id="feb5e-138">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)
