---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252011"
---
# \<customCookieHandler>
Imposta il tipo di gestore di cookie personalizzato. Questo elemento può essere presente solo se l' `mode` attributo dell' `<cookieHandler>` elemento è "Custom". Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Services.CookieHandler> classe. Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> utilizzato da per la lettura e la scrittura dei cookie.|  
  
## <a name="remarks"></a>Commenti  
 Quando si specifica un gestore di cookie personalizzato impostando l' `mode` attributo dell' `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie. Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Chunked" o "default". I gestori di cookie personalizzati devono derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 L' `<customCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene configurato il SAM per l'utilizzo di un gestore di cookie personalizzato di tipo `MyNamespace.MyCustomCookieHandler` .  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.CookieHandler>
