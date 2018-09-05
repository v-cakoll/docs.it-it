---
title: '&lt;tcpTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 92590f556d93859e8681eea8f8f05da4f560e150
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43738178"
---
# <a name="lttcptransportgt"></a>&lt;tcpTransport&gt;
Definisce un trasporto TCP che può essere usato da un canale ai messaggi dei trasferimenti per un'associazione personalizzata.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<tcpTransport>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tcpTransport   
      channelInitializationTimeout="TimeSpan"   
      connectionBufferSize="Integer"   
      hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
      listenBacklog="Integer"  
      manualAddressing="Boolean"   
      maxBufferPoolSize="Integer"  
      maxBufferSize="Integer"  
      maxOutputDelay="TimeSpan"  
      maxPendingAccepts="Integer"   
      maxPendingConnections="Integer"  
      maxReceivedMessageSize="Integer"   
      portSharingEnabled="Boolean"  
      teredoEnabled="Boolean"  
      transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >  
      <connectionPoolSettings  
            groupName="String"  
            idleTimeout"TimeSpan"  
            leaseTimeout="TimeSpan"  
            maxOutboundConnectionsPerEndpopint="Integer" />  
</tcpTransport>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|channelInitializationTimeout|Ottiene o imposta il limite di tempo per l'inizializzazione di un canale da accettare.  Periodo massimo di tempo entro il quale un canale può trovarsi nello stato di inizializzazione prima della disconnessione, espresso in secondi. La quota include il tempo necessario per l'autenticazione di una connessione TCP usando il protocollo .Net Message Framing. Un client deve inviare alcuni dati iniziali prima che il server disponga di informazioni sufficienti per effettuare l'autenticazione. Il valore predefinito è 30 secondi.|  
|connectionBufferSize|Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.|  
|hostNameComparisonMode|Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.|  
|listenBacklog|Numero massimo di richieste di connessione in coda che possono essere in sospeso per un servizio Web. L'attributo `connectionLeaseTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione. Si tratta di una proprietà a livello di socket che controlla il numero massimo di richieste di connessione in coda che possono essere in attesa di un servizio Web. Quando il valore di ListenBacklog è troppo basso, WCF arresta l'accettazione di richieste e pertanto ignora le nuove connessioni finché il server non riconosce alcune delle connessioni esistenti in coda. Per impostazione predefinita il valore è 16 * numero di processori.|  
|manualAddressing|Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.|  
|maxBufferPoolSize|Ottiene o imposta la dimensione massima di qualsiasi pool di buffer utilizzato dal trasporto.|  
|maxBufferSize|Ottiene o imposta la dimensione massima del buffer da utilizzare. Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.|  
|maxOutputDelay|Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.|  
|maxPendingAccepts|Ottiene o imposta il numero massimo di operazioni asincrone in sospeso disponibili per l'elaborazione delle connessioni in ingresso nel servizio.|  
|maxPendingConnections|Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.|  
|maxReceivedMessageSize|Ottiene e imposta la dimensione massima consentita del messaggio che può essere ricevuto.|  
|portSharingEnabled|Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione. Se è `false`, ciascuna associazione userà la propria porta esclusiva. Il valore predefinito è `false`.<br /><br /> Questa impostazione è pertinente solo per i servizi. I client non ne sono interessati.<br /><br /> L'uso di questa impostazione richiede l'attivazione del servizio di condivisione porte TCP di Windows Communication Foundation (WCF) modificando il relativo Tipo di avvio su Manuale o Automatico.|  
|teredoEnabled|Valore booleano che specifica se Teredo (una tecnologia per l'indirizzamento dei client dietro a firewall) è attivata. Il valore predefinito è `false`.<br /><br /> Questa proprietà abilita Teredo per il socket TCP sottostante. Per altre informazioni, vedere [Panoramica di Teredo](https://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Questa proprietà è applicabile solo su [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] e [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]. [!INCLUDE[wv](../../../../../includes/wv-md.md)] ha un'opzione di configurazione a livello di computer per Teredo, pertanto quando viene eseguito Vista, questa proprietà viene ignorata. L'uso di Teredo richiede che lo stack IPv6 di Microsoft sia installato sia nei computer client che in quelli di servizio e che tutti siano configurati correttamente. Per altre informazioni sulla configurazione di Teredo, vedere [Panoramica di Teredo](https://go.microsoft.com/fwlink/?LinkId=95339). Per altre informazioni, vedere [centri tecnologici Windows Server 2003](https://go.microsoft.com/fwlink/?LinkId=49888).|  
|transferMode|Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.|  
|impostazioniPoolConnessioni|Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 Questo trasporto usa URI nel formato "net.tcp://nomehost:porta/percorso". Gli altri componenti URI sono facoltativi.  
  
 L'elemento `tcpTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto TCP. Il trasporto è ottimizzato per le comunicazioni da WCF a WCF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
