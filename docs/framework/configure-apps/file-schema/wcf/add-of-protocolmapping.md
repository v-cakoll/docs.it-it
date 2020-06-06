---
title: <add> di <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850373"
---
# <a name="add-of-protocolmapping"></a>\<add> di \<protocolMapping>
Rappresenta un mapping del protocollo predefinito tra uno schema del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e un'associazione Windows Communication Foundation (WCF). Quando si creano endpoint predefiniti in fase di esecuzione, WCF esamina i mapping configurati e decide il binding da usare per un determinato indirizzo di base.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
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
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|binding|Stringa che specifica il tipo di associazione da usare per un endpoint durante la creazione dell'endpoint predefinito.|  
|bindingConfiguration|Stringa che specifica il nome della sezione di configurazione dell'associazione alla quale fare riferimento.|  
|scheme|Schema del protocollo di trasporto da usare per l'endpoint predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|Rappresenta una sezione di configurazione per la definizione di mapping dei protocolli predefiniti tra gli schemi del protocollo di trasporto (ad esempio http, NET. TCP, NET. pipe e così via) e le associazioni Windows Communication Foundation (WCF).|  
  
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
