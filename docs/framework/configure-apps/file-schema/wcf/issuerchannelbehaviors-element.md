---
title: Elemento &lt;issuerChannelBehaviors&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bb90b318f99816a3886056394559fdc80fa986ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a>Elemento &lt;issuerChannelBehaviors&gt;
Contiene una raccolta di comportamenti di endpoint del client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (definiti nella configurazione) da usare durante la comunicazione con i servizi STS specificati. Non possono contenere i comportamenti definiti [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials >  
\<issuedToken >  
\<issuerChannelBehaviors >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|Aggiunge un comportamento alla raccolta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Specifica un token personalizzato usato per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`, Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.  
  
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
