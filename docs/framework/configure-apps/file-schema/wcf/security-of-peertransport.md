---
title: '&lt;security&gt; di &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 8b0b8c5f230e8e93c07e13212201896010429af0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585380"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; di &lt;peerTransport&gt;
Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<peerTransport>  
\<security>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`mode`|Specifica il tipo di sicurezza da applicare. Il valore predefinito è Message. L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Attributo mode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`None`|La sicurezza è disabilitata.|  
|`Transport`|La sicurezza è fornita mediante HTTPS.|  
|`Message`|La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.|  
|`TransportWithMessageCredential`|HTTPS fornisce autenticazione e riservatezza. I messaggi SOAP forniscono tipi di credenziale dettagliati.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Definisce un trasporto peer per un'associazione personalizzata. Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio. L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peerTransport>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Definisce un trasporto peer per un'associazione personalizzata.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
