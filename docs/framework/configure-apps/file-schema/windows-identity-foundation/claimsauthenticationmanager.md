---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Specifica un tipo personalizzato da cui deriva il <xref:System.Security.Claims.ClaimsAuthenticationManager> classe. Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se è presente alcun `type` attributo, o se il `type` riferimenti dell'attributo di <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non ha elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possibile definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso. Se non `type` attributo specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non ha elementi figlio. È possibile specificare il `type` attributo per registrare un tipo derivato dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare un comportamento personalizzato. Le classi derivate possono supportare configurazione tramite gli elementi figlio del `<claimsAuthenticationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio è la finestra di progettazione della classe.  
  
 Il `<claimsAuthenticationManager>` set di elementi di <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
