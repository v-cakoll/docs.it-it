---
title: '&lt;add&gt; di &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;add&gt; di &lt;issuerChannelBehaviors&gt;
Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.  
  
> [!NOTE]
>  Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials >  
\<issuedToken >  
\<issuerChannelBehaviors > elemento  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|issuerAddress|URI dell'emittente del token di sicurezza con cui comunicare.|  
|behaviorConfiguration|Nome di un comportamento di endpoint definito nello stesso file di configurazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Contiene una raccolta di comportamenti di endpoint di client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] da usare durante le comunicazioni con i servizi STS specificati.|  
  
## <a name="remarks"></a>Note  
 `issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare. `behaviorConfiguration` punta al comportamento di un endpoint usato dall'applicazione nei canali creati da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] per ottenere i token pubblicati dai servizi token di sicurezza.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)  
 [Procedura: Creare un client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Procedura: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
