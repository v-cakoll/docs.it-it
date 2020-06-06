---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400014"
---
# \<protocolMapping>
Rappresenta una sezione di configurazione per la definizione di un set di mapping dei protocolli predefiniti tra gli schemi dei protocolli di trasporto (ad esempio http, net.tcp, net.pipe e così via) e le associazioni di WCF. Quando si creano endpoint predefiniti in fase di esecuzione, Windows Communication Foundation (WCF) esamina i mapping configurati e decide il binding da usare per un indirizzo specifico.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|Contiene un mapping del protocollo predefinito tra lo schema di un protocollo di trasporto (ad esempio http, net.tcp, net.pipe e così via) e l'associazione di WCF. |  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Elemento radice di tutti gli elementi di configurazione WCF.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config. È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config. In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
