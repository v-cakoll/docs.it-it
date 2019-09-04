---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252154"
---
# <a name="caches"></a>\<memorizza nella cache >
Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<memorizza nella cache >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.|  
|[\<tokenReplayCache>](tokenreplaycache.md)|Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 Un `<caches>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento. Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.  
  
 L' `<caches>` elemento è rappresentato <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> dalla classe. Le cache configurate sono rappresentate <xref:System.IdentityModel.Configuration.IdentityModelCaches> dalla classe.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di<xref:System.IdentityModel.Tokens.SessionSecurityToken>sicurezza della sessione (). La configurazione è ricavata `ClaimsAwareWebFarm` dall'esempio.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
