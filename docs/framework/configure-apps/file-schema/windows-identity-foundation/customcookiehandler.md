---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942787"
---
# <a name="customcookiehandler"></a>\<customCookieHandler>
Imposta il tipo di gestore di cookie personalizzato. Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "Custom". Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<customCookieHandler>  
  
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
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Services.CookieHandler> classe. Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> utilizzato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> per la lettura e la scrittura dei cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un gestore di cookie personalizzato impostando `mode` l'attributo `<cookieHandler>` dell'elemento su "Custom", è necessario specificare il tipo del gestore di cookie personalizzato includendo un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore di cookie. Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Chunked" o "default". I <xref:System.IdentityModel.Services.CookieHandler> gestori di cookie personalizzati devono derivare dalla classe.  
  
 L' `<customCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Configuration.CustomTypeElement> dalla classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene configurato il SAM per l'utilizzo di un gestore di cookie `MyNamespace.MyCustomCookieHandler`personalizzato di tipo.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.CookieHandler>
