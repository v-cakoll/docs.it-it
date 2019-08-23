---
title: <issuerMetadata> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: d9d7d41277eff1de43f717816b35fdc10d52192e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928883"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a>\<> issuerMetadata di \<issuedTokenParameters >
\<system.serviceModel>  
\<Binding >  
\<customBinding>  
\<binding>  
\<security>  
\<issuedTokenParameters>  
\<issuerMetadata>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|Address|Richiesto. Stringa che specifica l'indirizzo dell'endpoint. L'indirizzo deve essere un URI assoluto. Il valore predefinito è una stringa vuota.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<intestazioni >](headers-element.md)|Raccolte di intestazioni di indirizzo.|  
|[\<identity>](identity.md)|Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Funzionalità di sicurezza con associazioni personalizzate](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Associazioni](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicurezza delle associazioni personalizzate](../../../wcf/samples/custom-binding-security.md)
