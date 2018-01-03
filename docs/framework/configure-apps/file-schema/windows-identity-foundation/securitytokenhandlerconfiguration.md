---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ac7284fa418c1540582c40bd744e913ba31aa881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Fornisce la configurazione per la raccolta di gestori di token.  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
  
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
|saveBootstrapContext|Specifica se i token di bootstrap devono essere inclusi nel token di sessione. Il valore può inoltre essere impostato su una raccolta di gestore del token impostando il `saveBootstrapContext` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.|  
|maximumClockSkew|Oggetto <xref:System.TimeSpan> che specifica l'inclinazione di clock massima. Controlla lo sfasamento dei segnali di clock massima per le operazioni di scadenza, ad esempio convalida l'ora di scadenza di una sessione di accesso. Il valore predefinito è 5 minuti, "00: 05:00". Per ulteriori informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Lo sfasamento dei segnali di clock massima può essere impostato anche a livello di servizio mediante l'impostazione di `maximumClockSkew` attributo la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Specifica il set di URI accettabili identificatori delle relying party. Facoltativo.|  
|[\<memorizza nella cache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra le cache usate per i token di sessione e il rilevamento riproduzione token. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Facoltativo.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio servizio di convalida. Facoltativo.|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Consente di configurare il Registro di sistema nome dell'autorità di certificazione che viene utilizzata dai gestori nella raccolta di gestori di token. Facoltativo.|  
|[\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registra il resolver del token dell'autorità di certificazione che viene utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token dell'autorità di certificazione viene utilizzato per risolvere il token di firma di token in arrivo e messaggi. Facoltativo.|  
|[\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registra il resolver dei token di servizio che viene utilizzata dai gestori nella raccolta di gestori di token. Il resolver dei token di servizio viene utilizzato per risolvere il token di crittografia di token in arrivo e messaggi. Facoltativo.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Facoltativo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.|  
  
## <a name="remarks"></a>Note  
 In questa sezione fornisce i valori delle proprietà per un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> oggetto. Le impostazioni configurate in questa sezione sostituiscono quelli configurati nel servizio. Alcune di queste impostazioni possono, a sua volta, eseguire l'override delle impostazioni specificate quando si aggiunge un gestore per la raccolta di gestore del token di sicurezza.  
  
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
