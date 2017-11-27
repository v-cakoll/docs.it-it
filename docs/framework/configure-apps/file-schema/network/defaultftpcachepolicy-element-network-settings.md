---
title: '&lt;defaultFtpCachePolicy&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6b9a5fb2f62c27d278570ad789deab30917bc432
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a>&lt;defaultFtpCachePolicy&gt; elemento (impostazioni di rete)
Indica se la memorizzazione nella cache FTP è attivo e descrive il valore predefinito di criteri di memorizzazione nella cache.  
  
 \<configuration>  
\<System.NET >  
\<requestCaching >  
\<defaultFtpCachePolicy >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`policyLevel`|Specifica il protocollo FTP criteri di memorizzazione nella cache. Il valore predefinito è `Default`.|  
  
## <a name="policylevel-attribute"></a>Attributo policyLevel  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`Default`|Restituisce la risorsa memorizzata nella cache se la risorsa viene aggiornata, la lunghezza del contenuto è precisa e la scadenza, modifica e gli attributi di lunghezza del contenuto sono presenti.|  
|`BypassCache`|Restituisce la risorsa dal server.|  
|`CacheOnly`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione dell'elemento.|  
|`CacheIfAvailable`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto viene fornita e corrisponde alla dimensione dell'elemento; in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Restituisce la risorsa memorizzata nella cache, se il timestamp della risorsa nella cache è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, memorizzata nella cache e restituita al chiamante.|  
|`Reload`|Scarica la risorsa dal server, viene memorizzato nella cache e la restituisce al chiamante.|  
|`NoCacheNoStore`|Se esiste una risorsa memorizzati nella cache, viene eliminato. La risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Soddisfa una richiesta tramite la copia memorizzata nella cache della risorsa, se il timestamp è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, presentata al chiamante e memorizzata nella cache.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache delle richieste di rete.|  
  
## <a name="remarks"></a>Note  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un FTP la memorizzazione nella cache dei criteri di `NoCacheNoStore`.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
