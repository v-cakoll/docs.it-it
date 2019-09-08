---
title: 'Servizio: Listener di canale e canali'
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 0a740f5dcf682c3c140adb9c4c7c9678c4eae132
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797178"
---
# <a name="service-channel-listeners-and-channels"></a>Servizio: Listener di canale e canali

Sono disponibili tre categorie di oggetti canale: canali, listener del canale e Channel factory. I canali sono l'interfaccia tra l'applicazione e lo stack dei canali. I listener del canale sono responsabili della creazione di canali sul lato che riceve (o in ascolto), in genere in risposta a un messaggio in arrivo nuovo o a una connessione. I channel factory sono responsabili della creazione di canali sul lato di invio per iniziare la comunicazione con un endpoint.

## <a name="channel-listeners-and-channels"></a>Listener di canale e canali

I listener del canale sono responsabili della creazione di canali e della ricezione di messaggi dal livello inferiore o dalla rete. I messaggi ricevuti sono recapitati al livello superiore utilizzando un canale creato dal listener del canale.

Nel diagramma seguente è illustrato il processo di ricezione dei messaggi e del loro recapito al livello superiore.

![Listener del canale e canali](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")

Listener di canale che riceve messaggi e li recapita al livello superiore tramite canali.

Il processo può essere rappresentato concettualmente come una coda all'interno di ogni canale, anche se l'implementazione non utilizza effettivamente una coda. Un listener del canale è responsabile della ricezione di messaggi dal livello inferiore o dalla rete e del loro inserimento nella coda. Il canale è responsabile del recupero dei messaggi dalla coda e della consegna dei messaggi al livello superiore quando questo richiede un messaggio, ad esempio chiamando `Receive` sul canale.

WCF fornisce helper della classe di base per questo processo. Per un diagramma delle classi helper del canale descritte in questo articolo, vedere Panoramica del [modello di canale](channel-model-overview.md).

- La <xref:System.ServiceModel.Channels.CommunicationObject> classe implementa <xref:System.ServiceModel.ICommunicationObject> e impone la macchina a stati descritta nel passaggio 2 dello [sviluppo di canali](developing-channels.md).

- La <xref:System.ServiceModel.Channels.ChannelManagerBase> classe implementa <xref:System.ServiceModel.Channels.CommunicationObject> e fornisce una classe base unificata per <xref:System.ServiceModel.Channels.ChannelFactoryBase> e <xref:System.ServiceModel.Channels.ChannelListenerBase>. La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.

- La <xref:System.ServiceModel.Channels.ChannelFactoryBase> classe implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> `CreateChannel` `OnCreateChannel` e <xref:System.ServiceModel.Channels.IChannelFactory> e consolida gli overload in un unico metodo astratto.

- La <xref:System.ServiceModel.Channels.ChannelListenerBase> classe implementa <xref:System.ServiceModel.Channels.IChannelListener>. Si occupa della gestione dello stato di base.

La discussione seguente si basa [sul trasporto: Esempio](../samples/transport-udp.md) di UDP.

## <a name="creating-a-channel-listener"></a>Creazione di un listener del canale

L' `UdpChannelListener` oggetto implementato dall'esempio deriva <xref:System.ServiceModel.Channels.ChannelListenerBase> dalla classe. Utilizza un solo socket UDP per ricevere datagrammi. Il metodo `OnOpen` riceve dati utilizzando il socket UDP in un ciclo asincrono. I dati vengono quindi convertiti in messaggi utilizzando il sistema di codifica messaggi:

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

Poiché lo stesso canale del datagramma rappresenta messaggi in arrivo da un certo numero di origini, `UdpChannelListener` è un listener singleton. A questo listener è associato al <xref:System.ServiceModel.Channels.IChannel> massimo un elemento attivo alla volta. Nell'esempio ne viene generato un altro solo se un canale restituito dal metodo <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> viene successivamente eliminato. Quando viene ricevuto un messaggio, questo viene accodato in questo canale singleton.

### <a name="udpinputchannel"></a>UdpInputChannel

La `UdpInputChannel` classe implementa <xref:System.ServiceModel.Channels.IInputChannel>. È composta da una coda di messaggi in arrivo popolata dal socket di `UdpChannelListener`. La coda di questi messaggi viene annullata dal metodo <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>.
