---
title: '&lt;namedPipeTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d2d4be08012c1d33341ddd17713903782027c31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamedpipetransportgt"></a>&lt;namedPipeTransport&gt;
Definisce un trasporto che induce un canale a trasferire messaggi usando named pipe quando è incluso in un'associazione personalizzata.  
  
\<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<namePipeTransport >  
  
## <a name="syntax"></a>Sintassi  
  
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
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|ChannelInitializationTimeout|Ottiene o imposta un <xref:System.TimeSpan> che determina il tempo massimo di un canale può essere nello stato di inizializzazione prima della disconnessione.|  
|ConnectionBufferSize|Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.|  
|hostNameComparisonMode|Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.|  
|manualAddressing|Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.|  
|maxBufferPoolSize|Ottiene o imposta la dimensione massima, in byte, di tutti i pool di buffer utilizzati dal trasporto.|  
|maxBufferSize|Ottiene o imposta la dimensione massima del buffer da utilizzare. Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.|  
|maxOutputDelay|Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.|  
|maxPendingAccepts|Ottiene o imposta il numero massimo di canali di che un servizio può avere in attesa su un listener per l'elaborazione delle connessioni in ingresso per il servizio.|  
|maxPendingConnections|Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.|  
|maxReceivedMessageSize|Ottiene e imposta la dimensione massima consentita del messaggio, in byte, che possono essere ricevuti.|  
|transferMode|Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.|  
|[\<connectionPoolSettings > di \<namedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<associazione >](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
Questo trasporto usa URI nel formato "net.pipe://nomehost/percorso". Gli altri componenti URI sono facoltativi.  
  
L'elemento `namedPipeTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto delle named pipe. Questo trasporto viene usato per la comunicazione da computer con Windows Communication Foundation (WCF) a WCF.  
  
## <a name="see-also"></a>Vedere anche  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
[Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)   
[Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
[Associazioni](../../../../../docs/framework/wcf/bindings.md)   
[Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
[Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
[\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
