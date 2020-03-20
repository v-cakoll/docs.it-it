---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152749"
---
# <a name="claimsauthenticationmanager"></a>\<> di claimsAuthenticationManager
Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che <xref:System.Security.Claims.ClaimsAuthenticationManager> deriva dalla classe. Per ulteriori informazioni su `type` come specificare l'attributo, vedere [Riferimenti ai tipi personalizzati].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Se non `type` è presente alcun `type` attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> o `<claimsAuthenticationManager>` se l'attributo fa riferimento alla classe, l'elemento non accetta elementi figlio; tuttavia, le <xref:System.Security.Claims.ClaimsAuthenticationManager> classi derivate da possono definire elementi di configurazione figlio.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di identitàConfigurazione](identityconfiguration.md)|Specifica le impostazioni dell'identità a livello di servizio.|  
  
## <a name="remarks"></a>Osservazioni  
 Il comportamento predefinito <xref:System.Security.Claims.ClaimsAuthenticationManager> fornito tramite la classe fa eco alle attestazioni in ingresso. Se `type` non viene specificato `type` alcun attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> o `<claimsAuthenticationManager>` se l'attributo specifica la classe , l'elemento non accetta elementi figlio. È possibile `type` specificare l'attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> per registrare un tipo derivato dalla classe per implementare il comportamento personalizzato. Le classi derivate possono supportare la configurazione tramite gli elementi figlio dell'elemento `<claimsAuthenticationManager>` eseguendo l'override del <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi. Lo schema definito per gli elementi figlio è all'utente della finestra di progettazione della classe.  
  
 L'elemento `<claimsAuthenticationManager>` <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> imposta la proprietà .  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
