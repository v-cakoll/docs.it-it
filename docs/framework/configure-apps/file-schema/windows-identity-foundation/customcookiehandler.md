---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029086"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Imposta il tipo di gestore di cookie personalizzato. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Custom". Il tipo personalizzato deve derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 \<IdentityModel >  
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
|tipo|Specifica un tipo personalizzato che deriva dal <xref:System.IdentityModel.Services.CookieHandler> classe. Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> viene utilizzato per leggere e scrivere i cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un gestore di cookie personalizzato impostando il `mode` attributo del `<cookieHandler>` elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato, includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie. Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Chunked" o "Default". I gestori di cookie personalizzato devono derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 Il `<customCookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente configura il modulo SAM per utilizzare un gestore di cookie personalizzato di tipo `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.CookieHandler>
