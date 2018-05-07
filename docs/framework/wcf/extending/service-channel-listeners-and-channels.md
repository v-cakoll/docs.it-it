---
title: 'Servizio: listener del canale e canali'
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 5f5acff6ca933006707a863ea5ba04cd01cfb93e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="service-channel-listeners-and-channels"></a>Servizio: listener del canale e canali
Esistono tre categorie di oggetti del canale: canali, listener del canale e channel factory. I canali sono l'interfaccia tra l'applicazione e lo stack dei canali. I listener del canale sono responsabili della creazione di canali sul lato che riceve (o in ascolto), in genere in risposta a un messaggio in arrivo nuovo o a una connessione. I channel factory sono responsabili della creazione di canali sul lato di invio per iniziare la comunicazione con un endpoint.  
  
## <a name="channel-listeners-and-channels"></a>Listener del canale e canali  
 I listener del canale sono responsabili della creazione di canali e della ricezione di messaggi dal livello inferiore o dalla rete. I messaggi ricevuti sono recapitati al livello superiore utilizzando un canale creato dal listener del canale.  
  
 Nel diagramma seguente è illustrato il processo di ricezione dei messaggi e del loro recapito al livello superiore.  
  
 ![Listener del canale e canali](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")  
Listener di canale che riceve messaggi e li recapita al livello superiore tramite canali.  
  
 Il processo può essere rappresentato concettualmente come una coda all'interno di ogni canale, anche se l'implementazione non utilizza effettivamente una coda. Un listener del canale è responsabile della ricezione di messaggi dal livello inferiore o dalla rete e del loro inserimento nella coda. Il canale è responsabile del recupero dei messaggi dalla coda e della consegna dei messaggi al livello superiore quando questo richiede un messaggio, ad esempio chiamando `Receive` sul canale.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce supporti di classi di base per questo processo. (Per un diagramma di classi di supporto canale descritti in questo argomento, vedere [Cenni preliminari sul modello di canale](../../../../docs/framework/wcf/extending/channel-model-overview.md).)  
  
-   Il <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> e impone la macchina a stati descritta nel passaggio 2 di [sviluppo canali](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   Il <xref:System.ServiceModel.Channels.ChannelManagerBase> implementa <xref:System.ServiceModel.Channels.CommunicationObject> e fornisce una classe di base unificata per <xref:System.ServiceModel.Channels.ChannelFactoryBase> e <xref:System.ServiceModel.Channels.ChannelListenerBase>. La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.  
  
-   Il '<xref:System.ServiceModel.Channels.ChannelFactoryBase> implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> e <xref:System.ServiceModel.Channels.IChannelFactory> e li consolida il `CreateChannel` overload in uno `OnCreateChannel` metodo astratto.  
  
-   Il <xref:System.ServiceModel.Channels.ChannelListenerBase> implementa <xref:System.ServiceModel.Channels.IChannelListener>. Si occupa della gestione dello stato di base.  
  
 La seguente discussione si basa il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.  
  
## <a name="creating-a-channel-listener"></a>Creazione di un listener del canale  
 Il ' deriva listener canale UDP che l'esempio implementa il <xref:System.ServiceModel.Channels.ChannelListenerBase> classe. Utilizza un solo socket UDP per ricevere datagrammi. Il metodo `OnOpen` riceve dati utilizzando il socket UDP in un ciclo asincrono. I dati vengono quindi convertiti in messaggi utilizzando il sistema di codifica messaggi:  
  
```  
message = UdpConstants.MessageEncoder.ReadMessage(  
  new ArraySegment<byte>(buffer, 0, count),   
  bufferManager  
);  
```  
  
 Poiché lo stesso canale del datagramma rappresenta messaggi in arrivo da un certo numero di origini, `UdpChannelListener` è un listener singleton. Nella maggior parte di uno attivo <xref:System.ServiceModel.Channels.IChannel>' associata a questo listener in un momento. Nell'esempio ne viene generato un altro solo se un canale restituito dal metodo <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> viene successivamente eliminato. Quando un messaggio viene ricevuto, viene accodato in questo canale singleton.  
  
### <a name="udpinputchannel"></a>UdpInputChannel  
 Il `UdpInputChannel` implementa <xref:System.ServiceModel.Channels.IInputChannel>. È composta da una coda di messaggi in arrivo popolata dal socket di `UdpChannelListener`. La coda di questi messaggi viene annullata dal metodo <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>.
