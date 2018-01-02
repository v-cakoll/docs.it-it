---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 702b5ea1331aa0ac284d62809367a90e200a8ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltxmlelementgt"></a>&lt;xmlElement&gt;
Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.  
  
 \<System. ServiceModel >  
\<associazioni >  
\<wsFederatedBinding >  
\<associazione >  
\<sicurezza >  
\<messaggio >  
\<tokenRequestParameters >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|xmlElement|Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<tokenRequestParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|Raccolta di parametri della richiesta di token. Ciascun parametro è un elemento XML.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Funzionalità di sicurezza con associazioni personalizzate](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)
