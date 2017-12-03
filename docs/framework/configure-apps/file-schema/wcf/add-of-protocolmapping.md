---
title: '&lt;add&gt; di &lt;protocolMapping&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 255cd8518bd9c6c6c199c75aa32ca086c801d23f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;add&gt; di &lt;protocolMapping&gt;
Rappresenta un mapping del protocollo predefinito tra una combinazione di protocollo di trasporto (ad esempio, http, net.tcp, NET. pipe, e così via) e un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] associazione. Durante la creazione di endpoint predefiniti in fase di esecuzione, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analizza i mapping configurati e determina l'associazione da usare per un particolare indirizzo di base.  
  
 \<System. ServiceModel >  
\<protocolMapping >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|associazione|Stringa che specifica il tipo di associazione da usare per un endpoint durante la creazione dell'endpoint predefinito.|  
|bindingConfiguration|Stringa che specifica il nome della sezione di configurazione dell'associazione alla quale fare riferimento.|  
|scheme|Schema del protocollo di trasporto da usare per l'endpoint predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Rappresenta una sezione di configurazione per la definizione dei mapping di protocolli predefiniti tra gli schemi di protocollo di trasporto (ad esempio, http, net.tcp, NET. pipe, e così via) e [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] associazioni.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente viene illustrato il mapping del protocollo predefinito nel file machine.config. È possibile eseguire l'override di questo mapping predefinito al livello di computer modificando il file machine.config. In alternativa, se si desidera eseguirne l'override solo nell'ambito di un'applicazione, è possibile eseguire l'override di questa sezione all'interno del file di configurazione dell'applicazione e modificare il mapping per i singoli schemi di protocollo.  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
