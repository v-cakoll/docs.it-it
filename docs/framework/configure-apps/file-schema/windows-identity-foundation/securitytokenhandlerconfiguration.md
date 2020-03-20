---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152567"
---
# <a name="securitytokenhandlerconfiguration"></a>\<> securityTokenHandlerConfiguration
Fornisce la configurazione per la raccolta di gestori di token.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>securityTokenHandlerConfiguration**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|saveBootstrapContext|Specifica se i token di bootstrap devono essere inclusi nel token di sessione. Il valore può anche essere impostato su `saveBootstrapContext` una raccolta di gestori di token impostando l'attributo sull'elemento [ \<di>identityConfiguration.](identityconfiguration.md) Un valore impostato nella raccolta di gestori di token esegue l'override del valore impostato nel servizio.|  
|maximumClockSkew (massimoClockSkew)|Oggetto <xref:System.TimeSpan> che specifica l'inclinazione massima consentita. Controlla l'asimmetria di clock massima consentita durante l'esecuzione di operazioni sensibili al tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso. Il valore predefinito è 5 minuti, "00:05:00". Per ulteriori informazioni su <xref:System.TimeSpan> come specificare i valori, vedere [Valori Di intervallo](../windows-workflow-foundation/index.md). L'asimmetria di clock massima può essere `maximumClockSkew` impostata anche a livello di servizio impostando l'attributo sull'elemento [ \<identityConfiguration>.](identityconfiguration.md) Un valore impostato nella raccolta di gestori di token esegue l'override del valore impostato nel servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<AudienceUris>](audienceuris.md)|Specifica il set di URI che sono identificatori accettabili di questa relying party. Facoltativa.|  
|[\<>nella cache](caches.md)|Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione di token. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Facoltativa.|  
|[\<certificateConvalida>](certificatevalidation.md)|Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Queste impostazioni vengono sottoposte a override se un gestore specifico è configurato con il proprio validator. Facoltativa.|  
|[\<IssuerNameRegistry>](issuernameregistry.md)|Configura il registro del nome dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token. Facoltativa.|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|Registra il resolver di token dell'autorità di certificazione utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso. Facoltativa.|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|Registra il resolver di token del servizio utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token del servizio viene utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso. Facoltativa.|  
|[\<>di tokenReplayDetection](tokenreplaydetection.md)|Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Facoltativa.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.|  
  
## <a name="remarks"></a>Osservazioni  
 In questa sezione vengono <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> forniti i valori delle proprietà per un oggetto. Le impostazioni configurate in questa sezione sostituiscono quelle configurate nel servizio. Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
