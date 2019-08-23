---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940312"
---
# <a name="websocketsettings"></a>\<webSocketSettings>
Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.  
  
\<system.ServiceModel>  
\<Binding >  
\<netHttpBinding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|createNotificationOnConnection|Specifica se una notifica viene inviata alla connessione.|  
|disablePayloadMasking|Specifica se il mascheramento di Web Socket è disabilitato.|  
|keepAliveInterval|Specifica l'intervallo keep-alive.|  
|maxPendingConnections|Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.|  
|receiveBufferSize|Specifica le dimensioni del buffer di ricezione.|  
|sendBufferSize|Specifica le dimensioni del buffer di invio.|  
|subProtocol|Specifica il sottoprotocollo Web Socket.|  
|transportUsage|Specifica quando usare Web Sockets.|  
  
## <a name="transportusage-attribute"></a>transportUsage Attribute  
  
|Value|Descrizione|  
|-----------|-----------------|  
|WhenDuplex|Usare il protocollo Web Socket quando il contratto è di tipo duplex.|  
|Always|Usare sempre il protocollo Web Socket indipendentemente dal contratto.|  
|Never|Non usare mai il protocollo Web Socket.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|\<netHttpBinding>|Specifica NetHttpBinding|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' \<elemento webSocketSettings >.  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
