---
title: <udpTransportSettings> di <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: b67bdf825948dffe18aabe91b0de236eb929bccc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854857"
---
# <a name="udptransportsettings-of-udpannouncementendpoint"></a>\<udpTransportSettings> di \<udpAnnouncementEndpoint>
Questo elemento di configurazione espone le impostazioni di trasporto UDP per [\<udpAnnouncementEndpoint>](udpannouncementendpoint.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<udpAnnouncementEndpoint>**](udpannouncementendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<updTransportSettings>**  

## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpAnnouncementEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpAnnouncementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|Integer che specifica il numero massimo di hash del messaggio usati dal trasporto per l'identificazione di messaggi duplicati.  Il rilevamento dei duplicati verrà eseguito al livello TransportManager. L'impostazione di questa proprietà su 0 disabilita il rilevamento di messaggi duplicati.<br /><br /> Questo attributo consente a sviluppatori e amministratori di sistema di disattivare gli algoritmi per il rilevamento di messaggi duplicati. È possibile che si desideri disattivare questa funzionalità per implementare un algoritmo di rilevamento dei duplicati personalizzato.<br /><br /> Il valore predefinito è 4112.|  
|maxBufferPoolSize|Integer che specifica le dimensioni massime dei pool di buffer usati dal trasporto.|  
|maxMulticastRetransmitCount|Integer che specifica il numero massimo di volte in cui il messaggio unicast deve essere ritrasmesso (oltre al primo invio).<br /><br /> Il valore predefinito è 2.|  
|maxPendingMessageCount|Integer che specifica il numero massimo di messaggi ricevuti ma non ancora rimossi da InputQueue per una singola istanza di canale.  Se InputQueue ha raggiunto il limite massimo di messaggi in sospeso, il messaggio verrà eliminato.<br /><br /> Il valore predefinito è 32.|  
|maxReceivedMessageSize|Integer che specifica le dimensioni massime di un messaggio che può essere elaborato dall'associazione.<br /><br /> Il valore predefinito è 65507.|  
|maxUnicastRetransmitCount|Integer che specifica il numero massimo di volte in cui il messaggio unicast deve essere ritrasmesso (oltre al primo invio).  Se il messaggio viene inviato a un indirizzo unicast e un messaggio di risposta viene ricevuto con un'intestazione RelatesTo corrispondente, la ritrasmissione può terminare prima che il messaggio venga ritrasmesso il numero di volte configurato.<br /><br /> Il valore predefinito è 1.|  
|multicastInterfaceId|Stringa che identifica in modo univoco la scheda di rete da usare durante l'invio e la ricezione di traffico multicast in computer multihomed. In fase di runtime il trasporto utilizzerà questo valore di attributo per individuare l'indice dell'interfaccia usata per impostare le opzioni del socket `IP_MULTICAST_IF` e `IPV6_MULTICAST_IF`.  Lo stesso indice dell'interfaccia verrà usato per l'unione di un gruppo multicast, se applicabile.<br /><br /> Il valore predefinito è `null`.|  
|socketReceiveBufferSize|Integer che specifica le dimensioni del buffer di ricezione nel socket WinSock sottostante.<br /><br /> Un utente di un canale di ricezione può usare questo attributo nell'associazione per controllare il comportamento del sistema alla ricezione dei dati.  Ad esempio, per un'applicazione che usa messaggi WCF in ingresso alla soglia massima, l'uso di un valore superiore per questo attributo consentirebbe ai messaggi di posizionarsi nel buffer WinSock in attesa che l'applicazione sia in grado di elaborarli.  L'utilizzo di un valore inferiore nella stessa situazione determinerebbe il rilascio dei messaggi. Questo attributo espone l'opzione del socket `SO_RCVBUF` WinSock sottostante. Questo valore di attributo deve essere almeno pari a `maxReceivedMessageSize`.   L'impostazione su un valore inferiore a `maxReceivedMessageSize` determinerà la generazione di un'eccezione in fase di esecuzione.<br /><br /> Il valore predefinito è 65536.|  
|timeToLive|Integer che specifica il numero di hop dei segmenti di rete che un pacchetto multicast può attraversare.  Questo attributo espone la funzionalità associata alle opzioni del socket `IP_MULTICAST_TTL` e `IP_TTL`.<br /><br /> Il valore predefinito è 1.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|Endpoint standard che dispone di un contratto di annuncio e di un'associazione del trasporto UDP fissi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
