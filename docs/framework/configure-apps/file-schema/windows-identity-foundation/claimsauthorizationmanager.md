---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: a745339cffdada56a9b7f27f3f879b9d437c2da2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032101"
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
Registra un gestore di autorizzazione delle attestazioni per le attestazioni in ingresso.  
  
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
|tipo|Un tipo personalizzato che deriva dal <xref:System.Security.Claims.ClaimsAuthorizationManager> classe. Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se è presente alcun `type` attributo, oppure se il `type` i riferimenti dell'attributo le <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthorizationManager>` elemento non accetta elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthorizationManager> possono definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito fornito tramite il <xref:System.Security.Claims.ClaimsAuthorizationManager> classe autorizza sempre le attestazioni in ingresso. Se nessun `type` attributo è specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthorizationManager> (classe), il `<claimsAuthorizationManager>` elemento non accetta elementi figlio. È possibile specificare il `type` attributo per registrare un tipo derivato dal <xref:System.Security.Claims.ClaimsAuthorizationManager> classe per implementare il comportamento personalizzato. Le classi derivate possono supportano la configurazione tramite gli elementi figlio del `<claimsAuthorizationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.  
  
> [!IMPORTANT]
>  Quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la configurazione di identità che fa riferimento il `<federationConfiguration>` elemento consente di configurare il gestore di autorizzazione delle attestazioni e i criteri utilizzati per rendere decisioni di autorizzazione. Ciò è vero, anche in scenari non Web gli scenari passivi, ad esempio le applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il `<claimsAuthorizationManager>` elemento (e gli elementi di criteri figlio, se presente) della configurazione dell'identità cui viene fatto riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per altre informazioni, vedere la [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Questo elemento viene impostata la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrata la configurazione per un'autorizzazione delle attestazioni gestore che implementa criteri composto da coppie risorsa-azione di ognuno dei quali specifica combinazioni booleane le attestazioni che un richiedente deve disporre del privilegio per eseguire l'operazione sulla risorsa. Il codice che implementa il gestore di autorizzazione delle attestazioni in grado di utilizzare questo criterio è reperibile nel `ClaimsBasedAuthorization` esempio.  
  
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
