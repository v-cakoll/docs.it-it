---
title: '&lt;intestazioni&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7fdd869553a672045c94a256b00638c9d0c4c24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltheadersgt"></a>&lt;intestazioni&gt;
Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base. Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari. Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate. Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente. Ogni elemento deve essere in formato XML corretto.  
  
 \<System. ServiceModel >  
\<client >  
\<endpoint >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|Region||  
|Member||  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Configura differenti tipi di endpoint.|  
  
## <a name="remarks"></a>Note  
 Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint. Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [Endpoint: indirizzi, associazioni e contratti](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
