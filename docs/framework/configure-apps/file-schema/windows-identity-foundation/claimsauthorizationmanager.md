---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252075"
---
# \<claimsAuthorizationManager>
Registra un gestore autorizzazioni delle attestazioni per le attestazioni in ingresso.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
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
|type|Tipo personalizzato che deriva dalla <xref:System.Security.Claims.ClaimsAuthorizationManager> classe. Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se non esiste alcun `type` attributo o se l' `type` attributo fa riferimento alla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthorizationManager>` elemento non accetta elementi figlio. Tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthorizationManager> possono definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Commenti  
 Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthorizationManager> classe autorizza sempre le attestazioni in ingresso. Se non `type` è specificato alcun attributo o se l' `type` attributo specifica la <xref:System.Security.Claims.ClaimsAuthorizationManager> classe, l' `<claimsAuthorizationManager>` elemento non accetta gli elementi figlio. È possibile specificare l' `type` attributo per registrare un tipo derivato dalla <xref:System.Security.Claims.ClaimsAuthorizationManager> classe per implementare il comportamento personalizzato. Le classi derivate possono supportare la configurazione tramite elementi figlio dell' `<claimsAuthorizationManager>` elemento eseguendo l'override del <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.  
  
> [!IMPORTANT]
> Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, la configurazione dell'identità a cui fa riferimento l' `<federationConfiguration>` elemento configura il gestore delle autorizzazioni delle attestazioni e i criteri usati per prendere decisioni di autorizzazione. Questo vale anche per gli scenari che non sono scenari Web passivi, ad esempio applicazioni Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, l' `<claimsAuthorizationManager>` elemento e i relativi elementi figlio, se presenti, della configurazione di identità a cui si fa riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per ulteriori informazioni, vedere l' [\<federationConfiguration>](federationconfiguration.md) elemento.  
  
 Questo elemento imposta la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> Proprietà.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione di un gestore autorizzazioni delle attestazioni che implementa i criteri composte da coppie di azioni di risorse, ognuna delle quali specifica le combinazioni booleane delle attestazioni che un richiedente deve possedere per eseguire l'azione sulla risorsa. Il codice che implementa il gestore autorizzazioni delle attestazioni in grado di utilizzare questo criterio è disponibile nell' `ClaimsBasedAuthorization` esempio.  
  
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
