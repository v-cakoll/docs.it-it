---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252097"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimsAuthenticationManager**  
  
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
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che deriva dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe. Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se non esiste alcun `type` attributo o se l' `type` attributo fa riferimento alla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthenticationManager>` elemento non accetta elementi figlio. Tuttavia, le classi derivate da possono definire elementi di <xref:System.Security.Claims.ClaimsAuthenticationManager> configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso. Se non `type` è specificato alcun attributo o se `type` l'attributo specifica <xref:System.Security.Claims.ClaimsAuthenticationManager> la classe, `<claimsAuthenticationManager>` l'elemento non accetta gli elementi figlio. È possibile specificare l' `type` attributo per registrare un tipo derivato <xref:System.Security.Claims.ClaimsAuthenticationManager> dalla classe per implementare il comportamento personalizzato. Le classi derivate possono supportare la configurazione tramite `<claimsAuthenticationManager>` elementi figlio dell'elemento eseguendo <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> l'override del metodo per gestire questi elementi. Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.  
  
 L' `<claimsAuthenticationManager>` elemento imposta la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
