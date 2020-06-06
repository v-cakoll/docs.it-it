---
title: <standardEndpoints>
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: 76a5303650c4e2b2887d29f511d3088c78b58fe2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399519"
---
# \<standardEndpoints>
Questa sezione di configurazione consente di definire una raccolta di endpoint standard rappresentati da endpoint preconfigurati riusabili. Un endpoint standard disporrà di uno o più indirizzi, attributi di associazione e del contratto impostati su un valore fisso. Ad esempio, nell'endpoint di individuazione il contratto è fisso. È inoltre possibile usare endpoint standard per estendere endpoint servizio con nuove proprietà in modo analogo alla definizione di associazioni personalizzate.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoints>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|Definisce un endpoint standard con un contratto di annuncio fisso. Un servizio può annunciare la propria disponibilità inviando un messaggio di annuncio online oppure offline rispettivamente quando viene aperto o chiuso. Un servizio Windows Communication Foundation (WCF) specifica gli endpoint dell'annuncio nell' [\<serviceDiscovery>](servicediscovery.md) elemento e USA AnnouncementClient per eseguire gli annunci. Un client che desidera restare in ascolto dell'annuncio da un altro servizio funziona effettivamente come servizio WCF; è quindi necessario configurare gli endpoint dell'annuncio per il client nella [\<services>](services.md) sezione.|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|Definisce un endpoint standard con contratto di individuazione fisso. Quando viene aggiunto alla configurazione del servizio, specifica la posizione di ascolto dei messaggi di individuazione. Quando viene aggiunto alla configurazione del client, specifica la posizione di invio delle query di individuazione.|  
|[\<dynamicEndpoint>](dynamicendpoint.md)|Questo elemento di configurazione definisce un endpoint standard contenente le informazioni che consentono a un'applicazione di essere usata come un programma client in grado di individuare l'indirizzo dell'endpoint in modo dinamico durante la fase di esecuzione.|  
|[\<mexEndpoint>](mexendpoint.md)|Definisce un endpoint standard con un contratto IMetadataExchange fisso. Poiché tutti gli endpoint per lo scambio di metadati specificano IMetadataExchange come contratto, è possibile usare questo endpoint standard anziché definirne uno personalizzato.|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|Definisce un endpoint standard usato dai servizi per l'invio di messaggi di annuncio su un'associazione UDP. Dispone di un contratto fisso e supporta due versioni di individuazione. Dispone inoltre di un'associazione UDP fissa e di un valore dell'indirizzo predefinito come indicato nelle specifiche WS-Discovery (WS-Discovery aprile 2005 o versione WS-Discovery 1.1). È possibile specificare l'indirizzo multicast da usare per l'invio e la ricezione dei messaggi di annuncio.|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|Definisce un endpoint standard preconfigurato per le operazioni di individuazione su un'associazione multicast UDP. Questo endpoint dispone di un contratto fisso e supporta due versioni del protocollo WS-Discovery. Dispone inoltre di un'associazione UDP fissa e di un indirizzo predefinito come indicato nelle specifiche WS-Discovery (WS-Discovery aprile 2005 o WS-Discovery V1.1).|  
|[\<webHttpEndpoint>](webhttpendpoint.md)|Definisce un endpoint standard con un' [\<webHttpBinding>](webhttpbinding.md) associazione fissa che aggiunge automaticamente il [\<webHttp>](webhttp.md) comportamento. Usare questo endpoint per la scrittura di un servizio REST.|  
|[\<webScriptEndpoint>](webscriptendpoint.md)|Definisce un endpoint standard con un' [\<webHttpBinding>](webhttpbinding.md) associazione fissa che aggiunge automaticamente il [\<enableWebScript>](enablewebscript.md) comportamento. Usare questo endpoint per la scrittura di un servizio chiamato da un'applicazione AJAX ASP.NET.|  
|[\<workflowControlEndpoint>](workflowcontrolendpoint.md)|Definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|\<system.ServiceModel>|Elemento radice di tutti gli elementi di configurazione WCF.|  
  
## <a name="see-also"></a>Vedi anche

- [Endpoint standard](../../../wcf/feature-details/standard-endpoints.md)
