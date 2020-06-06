---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: f2c1335795ffd3cb395a7006bfaeb3cf7b39636b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77448621"
---
# \<tcpTransport>
Definisce un trasporto TCP che può essere usato da un canale ai messaggi dei trasferimenti per un'associazione personalizzata.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
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
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|channelInitializationTimeout|Ottiene o imposta il limite di tempo per l'inizializzazione di un canale da accettare.  Periodo massimo di tempo entro il quale un canale può trovarsi nello stato di inizializzazione prima della disconnessione, espresso in secondi. Questa quota include il tempo necessario per l'autenticazione di una connessione TCP tramite il protocollo di frame di messaggi .NET. Un client deve inviare alcuni dati iniziali prima che il server disponga di informazioni sufficienti per effettuare l'autenticazione. Il valore predefinito è 30 secondi.|  
|connectionBufferSize|Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.|  
|hostNameComparisonMode|Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.|  
|listenBacklog|Numero massimo di richieste di connessione in coda che possono essere in sospeso per un servizio Web. L'attributo `connectionLeaseTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione. Si tratta di una proprietà a livello di socket che controlla il numero massimo di richieste di connessione in coda che possono essere in attesa di un servizio Web. Quando ListenBacklog è troppo basso, WCF smette di accettare le richieste e pertanto rilascia nuove connessioni finché il server non riconosce alcune delle connessioni in coda esistenti. Il valore predefinito è 16 * numero di processori.|  
|manualAddressing|Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.|  
|maxBufferPoolSize|Ottiene o imposta la dimensione massima di qualsiasi pool di buffer utilizzato dal trasporto.|  
|maxBufferSize|Ottiene o imposta la dimensione massima del buffer da utilizzare. Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.|  
|maxOutputDelay|Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.|  
|maxPendingAccepts|Ottiene o imposta il numero massimo di operazioni asincrone in sospeso disponibili per l'elaborazione delle connessioni in ingresso nel servizio.|  
|maxPendingConnections|Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.|  
|maxReceivedMessageSize|Ottiene e imposta la dimensione massima consentita del messaggio che può essere ricevuto.|  
|portSharingEnabled|Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione. Se è `false`, ciascuna associazione userà la propria porta esclusiva. Il valore predefinito è `false`.<br /><br /> Questa impostazione è pertinente solo per i servizi. I client non ne sono interessati.<br /><br /> L'uso di questa impostazione richiede l'attivazione del servizio di condivisione porte TCP di Windows Communication Foundation (WCF) modificando il relativo Tipo di avvio su Manuale o Automatico.|  
|teredoEnabled|Valore booleano che specifica se Teredo (una tecnologia per l'indirizzamento dei client dietro a firewall) è attivata. Il valore predefinito è `false`.<br /><br /> Questa proprietà abilita Teredo per il socket TCP sottostante. Per altre informazioni, vedere [Panoramica di Teredo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).<br /><br /> Questa proprietà è applicabile solo in Windows XP SP2 e Windows Server 2003. Windows Vista dispone di un'opzione di configurazione a livello di computer per Teredo, pertanto quando si esegue vista, questa proprietà viene ignorata. L'uso di Teredo richiede che lo stack IPv6 di Microsoft sia installato sia nei computer client che in quelli di servizio e che tutti siano configurati correttamente.|  
|transferMode|Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.|  
|impostazioniPoolConnessioni|Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Commenti  
 Questo trasporto usa URI nel formato "net.tcp://nomehost:porta/percorso". Gli altri componenti URI sono facoltativi.  
  
 L'elemento `tcpTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto TCP. Il trasporto è ottimizzato per le comunicazioni da WCF a WCF.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Trasporti](../../../wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../wcf/feature-details/choosing-a-transport.md)
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
