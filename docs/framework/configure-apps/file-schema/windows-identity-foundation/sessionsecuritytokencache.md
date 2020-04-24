---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646071"
---
# <a name="sessionsecuritytokencache"></a>\<sessionSecurityTokenCache>
Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>nella cache**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>sessionSecurityTokenCache**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Tipo che deriva dalla <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>nella cache](caches.md)|Registra le cache usate da un servizio o da una raccolta di gestori di token di sicurezza.|  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione<xref:System.IdentityModel.Tokens.SessionSecurityToken>di una cache personalizzata per il contenimento dei token di sicurezza della sessione ( ). La configurazione viene `ClaimsAwareWebFarm` ricavata dall'esempio. Per ulteriori informazioni su questo esempio, vedere [Indice dell'esempio](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)di codice WIF .  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
