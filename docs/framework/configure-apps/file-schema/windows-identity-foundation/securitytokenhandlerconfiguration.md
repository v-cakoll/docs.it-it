---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152567"
---
# \<securityTokenHandlerConfiguration>
Fornisce la configurazione per la raccolta di gestori di token.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
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
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|saveBootstrapContext|Specifica se i token di bootstrap devono essere inclusi nel token di sessione. Il valore può essere impostato anche in una raccolta di gestori di token impostando l' `saveBootstrapContext` attributo sull' [\<identityConfiguration>](identityconfiguration.md) elemento. Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.|  
|maximumClockSkew|Oggetto <xref:System.TimeSpan> che specifica lo sfasamento massimo consentito del clock. Controlla lo sfasamento massimo consentito di clock quando si eseguono operazioni dipendenti dal tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso. Il valore predefinito è 5 minuti, "00:05:00". Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md). Lo sfasamento di clock massimo può essere impostato anche a livello di servizio impostando l' `maximumClockSkew` attributo sull' [\<identityConfiguration>](identityconfiguration.md) elemento. Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|Specifica il set di URI che sono identificatori accettabili di questo relying party. Facoltativa.|  
|[\<caches>](caches.md)|Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Facoltativa.|  
|[\<certificateValidation>](certificatevalidation.md)|Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator. Facoltativa.|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token. Facoltativa.|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token. Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso. Facoltativa.|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso. Facoltativa.|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Facoltativa.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.|  
  
## <a name="remarks"></a>Commenti  
 In questa sezione vengono forniti i valori delle proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto. Le impostazioni configurate in questa sezione eseguono l'override di quelle configurate nel servizio. Alcune di queste impostazioni possono, a loro volta, essere sottoposte a override dalle impostazioni specificate quando un gestore viene aggiunto alla raccolta di gestori di token di sicurezza.  
  
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
