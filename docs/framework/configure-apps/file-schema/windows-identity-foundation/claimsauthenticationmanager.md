---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255185"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager>  
  
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
|tipo|Specifica un tipo personalizzato che deriva dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe. Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se è presente alcun `type` attributo, oppure se il `type` i riferimenti dell'attributo le <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possono definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito fornito tramite il <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso. Se nessun `type` attributo è specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio. È possibile specificare il `type` attributo per registrare un tipo derivato dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare il comportamento personalizzato. Le classi derivate possono supportano la configurazione tramite gli elementi figlio del `<claimsAuthenticationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.  
  
 Il `<claimsAuthenticationManager>` set di elementi di <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
