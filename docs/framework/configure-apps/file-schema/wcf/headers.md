---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: a982fa87ab84725e36ee913f00200cd34f0b8f6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925570"
---
# <a name="headers"></a>\<intestazioni >
Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base. Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari. Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate. Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente. Ogni elemento deve essere in formato XML corretto.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Elementi XML definiti dall'utente.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|Configura differenti tipi di endpoint.|  
  
## <a name="remarks"></a>Note  
 Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint. Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [Endpoint Indirizzi, associazioni e contratti](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
