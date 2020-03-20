---
title: 'Client: channel factory e canali'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: 25e2c034d1fefc7728667231040a97c3aeecabbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185685"
---
# <a name="client-channel-factories-and-channels"></a>Client: channel factory e canali
In questo argomento viene illustrata la creazione di channel factory e canali.  
  
## <a name="channel-factories-and-channels"></a>Channel factory e canali  
 Le channel factory sono responsabili della creazione di canali. I canali creati da channel factory vengono usati per l'invio di messaggi. Questi canali ottengono il messaggio dal livello superiore, eseguono l'elaborazione necessaria, quindi inviano il messaggio al livello inferiore. Nel grafico seguente viene illustrato questo processo.  
  
 ![Factory e canali client](./media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")  
Una channel factory crea canali.  
  
 Quando sono chiuse, le channel factory sono responsabili della chiusura di tutti i canali creati non ancora chiusi. Il modello rappresentato è asimmetrico perché quando un listener del canale viene chiuso, smette solo di accettare nuovi canali, mentre lascia aperti i canali esistenti affinché possano continuare a ricevere messaggi.  
  
 WCF fornisce gli helper della classe di base per questo processo. Per un diagramma delle classi helper del canale descritte in questo argomento, vedere Cenni preliminari sul modello di [canale.](channel-model-overview.md)  
  
- La <xref:System.ServiceModel.Channels.CommunicationObject> classe <xref:System.ServiceModel.ICommunicationObject> implementa e applica la macchina a stati descritta nel passaggio 2 di [Developing Channels](developing-channels.md).  
  
- La <xref:System.ServiceModel.Channels.ChannelManagerBase> classe <xref:System.ServiceModel.Channels.CommunicationObject> implementa e fornisce una <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>classe base unificata per e . La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.
  
- La <xref:System.ServiceModel.Channels.ChannelFactoryBase> classe <xref:System.ServiceModel.Channels.ChannelManagerBase> <xref:System.ServiceModel.Channels.IChannelFactory> implementa e `CreateChannel` consolida gli `OnCreateChannel` overload in un unico metodo astratto.
  
- La <xref:System.ServiceModel.Channels.ChannelListenerBase> classe <xref:System.ServiceModel.Channels.IChannelListener>implementa . Si occupa della gestione dello stato di base.
  
 La discussione seguente si basa sull'esempio [Transport: UDP.](../samples/transport-udp.md)  
  
### <a name="creating-a-channel-factory"></a>Creazione di una channel factory  
 `UdpChannelFactory` deriva da <xref:System.ServiceModel.Channels.ChannelFactoryBase>. L'esempio esegue l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> per fornire accesso alla versione del messaggio del codificatore di messaggi. L'esempio esegue inoltre l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> per chiudere l'istanza di <xref:System.ServiceModel.Channels.BufferManager> quando la macchina a stati esegue la transizione.  
  
#### <a name="the-udp-output-channel"></a>Canale di output UDP  
 `UdpOutputChannel` implementa <xref:System.ServiceModel.Channels.IOutputChannel>. Il costruttore convalida gli argomenti e costruisce un oggetto <xref:System.Net.EndPoint> di destinazione basato sull'elemento <xref:System.ServiceModel.EndpointAddress> che viene passato.  
  
 L'override di <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> crea un socket che viene usato per inviare messaggi a questa classe <xref:System.Net.EndPoint>.  
  
 ```csharp
this.socket = new Socket(  
this.remoteEndPoint.AddressFamily,
   SocketType.Dgram,
   ProtocolType.Udp
);  
```  

 Il canale può essere chiuso normalmente o in modo anomalo. Se il canale viene chiuso normalmente, il socket viene chiuso e viene eseguita una chiamata al metodo `OnClose` della classe di base. Se viene generata un'eccezione, l'infrastruttura chiama `Abort` per verificare che il canale sia pulito.  
  
```csharp  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 `Send()` Implementare `BeginSend()` / `EndSend()`e . In questo modo si ottengono due sezioni principali. Prima serializzare il messaggio in una matrice di byte:  
  
```csharp  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 Inviare quindi i dati risultanti sulla rete.  
  
```csharp  
this.socket.SendTo(  
  messageBuffer.Array,
  messageBuffer.Offset,
  messageBuffer.Count,
  SocketFlags.None,
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Sviluppo di canali](developing-channels.md)
