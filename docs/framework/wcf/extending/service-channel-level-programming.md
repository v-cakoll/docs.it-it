---
title: Programmazione client a livello di canale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a1a6ef03b3ee0cc68809ec6ba80a7eadbc44cb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="service-channel-level-programming"></a>Programmazione client a livello di canale
In questo argomento viene descritto come scrivere un'applicazione di servizio di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] senza utilizzare la classe <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> e il relativo modello a oggetti associato.  
  
## <a name="receiving-messages"></a>Ricezione di messaggi  
 Per prepararsi alla ricezione e all'elaborazione di messaggi, è necessario eseguire i passaggi seguenti:  
  
1.  Creare un'associazione.  
  
2.  Generare un listener di canale.  
  
3.  Aprire il listener del canale.  
  
4.  Leggere la richiesta e inviare una risposta.  
  
5.  Chiudere tutti gli oggetti canale.  
  
#### <a name="creating-a-binding"></a>Creazione di un'associazione  
 Il primo passaggio dell'attesa e della ricezione di messaggi consiste nel creare un'associazione. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono disponibili molte associazioni predefinite o fornite dal sistema che è possibile utilizzare direttamente creando un'istanza. È inoltre possibile creare un'associazione personalizzata creando un'istanza della classe CustomBinding, operazione che viene eseguita nel codice dell'elenco 1.  
  
 Nell'esempio di codice seguente viene creata un'istanza di <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> e viene aggiunto un elemento <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> alla raccolta Elements, una raccolta di elementi di associazione utilizzati per generare lo stack di canali. Nell'esempio, poiché la raccolta degli elementi presenta solo <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, lo stack di canali risultante dispone solo del canale di trasporto HTTP.  
  
#### <a name="building-a-channellistener"></a>Generazione di un listener di canale.  
 Dopo aver creato un'associazione, viene chiamato <!--zz<xref:System.ServiceModel.Channels.Binding.BuildChannelListener%601%2A?displayProperty=nameWithType>--> `System.ServiceModel.Channels.Binding.BuildChannelListener` per compilare il listener del canale in cui il parametro di tipo è il canale da creare. In questo esempio si utilizza <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> perché si desidera ascoltare i messaggi in arrivo in un modello di scambio di messaggi Request/Reply.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel> viene utilizzato per ricevere messaggi di richiesta e restituire messaggi di risposta. La chiamata a <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=nameWithType> restituisce un elemento <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>, utilizzabile per ricevere il messaggio di richiesta e restituire un messaggio di risposta.  
  
 Quando si crea il listener, si passa l'indirizzo di rete su cui è in ascolto, in questo caso `http://localhost:8080/channelapp`. In genere, ogni canale del trasporto supporta uno o probabilmente più schemi di indirizzo, ad esempio il trasporto HTTP supporta entrambi gli schemi http e https.  
  
 Durante la creazione del listener si passa inoltre un elemento <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=nameWithType> vuoto. Un parametro dell'associazione è un meccanismo che consente di passare parametri che controllano la modalità di generazione del listener. Poiché nell'esempio questi parametri non vengono utilizzati, viene passata una raccolta vuota.  
  
#### <a name="listening-for-incoming-messages"></a>Ascolto di messaggi in arrivo  
 Si passa quindi a chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> sul listener e si inizia ad accettare canali. Il comportamento del metodo <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType> dipende dalla natura del trasporto, orientato alla connessione o senza connessione. Per trasporti orientati alla connessione, <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> si blocca fino all'arrivo di una nuova richiesta di connessione, quindi restituisce un nuovo canale che rappresenta la nuova connessione. Per trasporti senza connessione, ad esempio HTTP, <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> restituisce immediatamente l'unico canale che il listener del trasporto crea.  
  
 Nell'esempio il listener restituisce un canale che implementa <xref:System.ServiceModel.Channels.IReplyChannel>. Per ricevere messaggi su questo canale si chiama prima <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> sul canale per prepararlo alla comunicazione. Si chiama quindi <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> che si blocca fino all'arrivo di un messaggio.  
  
#### <a name="reading-the-request-and-sending-a-reply"></a>Lettura della richiesta e invio della risposta  
 Quando <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> restituisce un elemento <xref:System.ServiceModel.Channels.RequestContext>, si ottiene il messaggio ricevuto utilizzando la proprietà <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A>. Si scrivono l'azione e il contenuto del corpo del messaggio (presumibilmente una stringa).  
  
 Per inviare una risposta, si crea un messaggio di risposta, ovvero in questo caso passando i dati di tipo stringa ricevuti nella richiesta. Si chiama quindi <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> per inviare il messaggio di risposta.  
  
#### <a name="closing-objects"></a>Chiusura di oggetti  
 Per evitare la perdita di risorse, è molto importante chiudere gli oggetti utilizzati nelle comunicazioni quando non sono più necessari. Nell'esempio si chiudono il messaggio di richiesta, il contesto della richiesta, il canale e il listener.  
  
 Nell'esempio di codice seguente viene illustrato un servizio di base in cui un listener del canale riceve solo uno messaggio. Un servizio reale continua ad accettare canali e a ricevere messaggi fino alla chiusura del servizio.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]
