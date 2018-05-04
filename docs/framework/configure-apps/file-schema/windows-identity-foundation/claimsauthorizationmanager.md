---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 06824e20286f8905ad3a8ac9d2b4a30366a6ec10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
Registra un gestore autorizzazioni attestazioni per le attestazioni in ingresso.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthorizationManager >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Un tipo personalizzato da cui deriva il <xref:System.Security.Claims.ClaimsAuthorizationManager> classe. Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se è presente alcun `type` attributo, o se il `type` riferimenti dell'attributo di <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthorizationManager>` elemento non ha elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthorizationManager> possibile definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthorizationManager> classe autorizza sempre le attestazioni in ingresso. Se non `type` attributo specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthorizationManager> (classe), il `<claimsAuthorizationManager>` elemento non ha elementi figlio. È possibile specificare il `type` attributo per registrare un tipo derivato dalla <xref:System.Security.Claims.ClaimsAuthorizationManager> classe per implementare un comportamento personalizzato. Le classi derivate possono supportare configurazione tramite gli elementi figlio del `<claimsAuthorizationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio è la finestra di progettazione della classe.  
  
> [!IMPORTANT]
>  Quando si utilizza il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la configurazione di identità a cui fa riferimento il `<federationConfiguration>` elemento consente di configurare i criteri viene utilizzato per rendere e la gestione di autorizzazioni di attestazioni decisioni di autorizzazione. Questo è true, anche negli scenari che non sono passivi scenari Web, ad esempio applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il `<claimsAuthorizationManager>` elemento (e criteri elementi figlio, se presente) della configurazione dell'identità a cui fa riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per ulteriori informazioni, vedere il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Questo elemento viene impostata la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente mostra la configurazione per un'autorizzazione delle attestazioni di gestione che implementa criteri costituito da coppie di azione della risorsa di ognuno dei quali specifica booleane combinazioni delle attestazioni che disponga di un richiedente per eseguire l'operazione sulla risorsa. Il codice che implementa la gestione di autorizzazione delle attestazioni in grado di utilizzare questo criterio è reperibile nel `ClaimsBasedAuthorization` esempio.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
