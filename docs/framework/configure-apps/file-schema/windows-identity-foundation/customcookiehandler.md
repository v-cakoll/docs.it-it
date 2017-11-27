---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: df95e8d47d6a19e4fd488fa14bc771bc2c2b56b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Imposta il tipo di gestore cookie personalizzati. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Personalizzato". Il tipo personalizzato deve essere derivato dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 \<System >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
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
|type|Specifica un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Services.CookieHandler> classe. Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> utilizzata per leggere e scrivere i cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un gestore personalizzato cookie impostando il `mode` attributo del `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie. Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Chunked" o "Default". I gestori di cookie personalizzato devono derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 Il `<customCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di configurare il modulo SAM per utilizzare un gestore personalizzato di cookie di tipo `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.CookieHandler>
