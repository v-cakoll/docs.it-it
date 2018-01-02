---
title: '&lt;security&gt; di &lt;peerTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; di &lt;peerTransport&gt;
Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.  
  
 \<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<peerTransport >  
\<sicurezza >  
  
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
|[\<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Definisce un trasporto peer per un'associazione personalizzata. Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio. L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peerTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Definisce un trasporto peer per un'associazione personalizzata.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
