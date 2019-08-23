---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 68e3a0802a10b14148188a81ee24ed901caa147f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925374"
---
# <a name="issuedtoken"></a>\<issuedToken>
Specifica un token personalizzato usato per autenticare un client presso un servizio.  
  
 \<system.ServiceModel>  
\<comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials>  
\<issuedToken>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`cacheIssuedTokens`|Attributo booleano facoltativo che specifica se i token vengono memorizzati nella cache. Il valore predefinito è `true`.|  
|`defaultKeyEntropyMode`|Attributo stringa facoltativo che specifica quali valori casuali (entropie) sono usati per le operazioni di handshake. I valori comprendono `ClientEntropy`, `ServerEntropy` e `CombinedEntropy`. Il valore predefinito `CombinedEntropy`. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Attributo intero facoltativo che specifica la percentuale di un intervallo di tempo valido (fornito dall'emittente del token) che può trascorrere prima che un token venga rinnovato. I valori sono compresi tra 0 e 100. Il valore predefinito è 60 e indica che una volta trascorso il 60% dell'intervallo di tempo il sistema esegue un tentativo di rinnovo.|  
|`issuerChannelBehaviors`|Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente.|  
|`localIssuerChannelBehaviors`|Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente locale.|  
|`maxIssuedTokenCachingTime`|Attributo Timespan facoltativo che, quando l'emittente del token (un servizio token di sicurezza) non specifica alcun intervallo, definisce la durata di memorizzazione nella cache dei token emessi. Il valore predefinito è "10675199.02:48:05.4775807".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|Specifica l'indirizzo dell'emittente locale del token e l'associazione usata per comunicare con l'endpoint.|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Specifica i comportamenti di endpoint da usare quando si contatta un'emittente locale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Un token emesso è un tipo di credenziale personalizzato usato, ad esempio, quando si esegue l'autenticazione con un servizio token di sicurezza in uno scenario federato. Per impostazione predefinita, il token è un token SAML. Per altre informazioni, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md). e la [Federazione e i token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Questa sezione contiene gli elementi usati per configurare un'autorità emittente locale di token oppure i comportamenti usati in un servizio token di sicurezza. Per istruzioni sulla configurazione di un client per l'uso di un'autorità emittente [locale, vedere Procedura: Configurare un'autorità emittente](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)locale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Procedura: Creazione di un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedura: Configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
