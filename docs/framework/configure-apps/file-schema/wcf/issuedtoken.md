---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 56439748926ada642018f48a5787634a50d0f180
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "72846864"
---
# \<issuedToken>
Specifica un token personalizzato usato per autenticare un client presso un servizio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
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
|[\<localIssuer>](localissuer.md)|Specifica l'indirizzo dell'emittente locale del token e l'associazione usata per comunicare con l'endpoint.|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Specifica i comportamenti di endpoint da usare quando si contatta un'emittente locale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Commenti  
 Un token emesso è un tipo di credenziale personalizzato usato, ad esempio, quando si esegue l'autenticazione con un servizio token di sicurezza in uno scenario federato. Per impostazione predefinita, il token è un token SAML. Per altre informazioni, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md), [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Questa sezione contiene gli elementi usati per configurare un'autorità emittente locale di token oppure i comportamenti usati in un servizio token di sicurezza. Per istruzioni sulla configurazione di un client per l'uso di un'autorità emittente locale, vedere [procedura: configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Procedura: creare un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedura: configurare un emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
