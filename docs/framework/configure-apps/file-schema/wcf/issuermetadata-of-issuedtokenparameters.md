---
title: '&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e8df1ffb74c59bfed2b9fa2f1e87e7669fe3ad9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a>&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;
\<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<sicurezza >  
\<issuedTokenParameters >  
\<issuerMetadata >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|address|Obbligatorio. Stringa che specifica l'indirizzo dell'endpoint. L'indirizzo deve essere un URI assoluto. Il valore predefinito è una stringa vuota.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<intestazioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Raccolte di intestazioni di indirizzo.|  
|[\<identità >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuedTokenParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [L'autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Funzionalità di sicurezza con associazioni personalizzate](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Sicurezza delle associazioni personalizzate](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
