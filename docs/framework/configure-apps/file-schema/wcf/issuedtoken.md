---
title: '&lt;issuedToken&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9a8d701e0806aae0a17a1c5ff7284606dd080f85
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuedtokengt"></a>&lt;issuedToken&gt;
Specifica un token personalizzato usato per autenticare un client presso un servizio.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials>  
\<issuedToken >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`cacheIssuedTokens`|Attributo booleano facoltativo che specifica se i token vengono memorizzati nella cache. Il valore predefinito è `true`.|  
|`defaultKeyEntropyMode`|Attributo stringa facoltativo che specifica quali valori casuali (entropie) sono usati per le operazioni di handshake. I valori comprendono `ClientEntropy`, `ServerEntropy` e `CombinedEntropy`. Il valore predefinito `CombinedEntropy`. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Attributo intero facoltativo che specifica la percentuale di un intervallo di tempo valido (fornito dall'emittente del token) che può trascorrere prima che un token venga rinnovato. I valori sono compresi tra 0 e 100. Il valore predefinito è 60 e indica che una volta trascorso il 60% dell'intervallo di tempo il sistema esegue un tentativo di rinnovo.|  
|`issuerChannelBehaviors`|Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente.|  
|`localIssuerChannelBehaviors`|Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente locale.|  
|`maxIssuedTokenCachingTime`|Attributo Timespan facoltativo che, quando l'emittente del token (un servizio token di sicurezza) non specifica alcun intervallo, definisce la durata di memorizzazione nella cache dei token emessi. Il valore predefinito è "10675199.02:48:05.4775807".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<localIssuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Specifica l'indirizzo dell'emittente locale del token e l'associazione usata per comunicare con l'endpoint.|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Specifica i comportamenti di endpoint da usare quando si contatta un'emittente locale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Un token emesso è un tipo di credenziale personalizzato usato, ad esempio, quando si esegue l'autenticazione con un servizio token di sicurezza in uno scenario federato. Per impostazione predefinita, il token è un token SAML. Per ulteriori informazioni, vedere [federazione e i token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). e [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Questa sezione contiene gli elementi usati per configurare un'autorità emittente locale di token oppure i comportamenti usati in un servizio token di sicurezza. Per istruzioni sulla configurazione di un client di utilizzare un emittente locale, vedere [procedura: configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)  
 [Procedura: Creare un client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Procedura: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
