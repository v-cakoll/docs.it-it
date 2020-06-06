---
title: Elemento <defaultFtpCachePolicy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088434"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>Elemento \<defaultFtpCachePolicy> (impostazioni di rete)
Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

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
|`policyLevel`|Specifica i criteri di memorizzazione nella cache FTP. Il valore predefinito è `Default`.|  
  
## <a name="policylevel-attribute"></a>policyLevel (attributo)  
  
|Valore|Description|  
|-----------|-----------------|  
|`Default`|Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.|  
|`BypassCache`|Restituisce la risorsa dal server.|  
|`CacheOnly`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.|  
|`CacheIfAvailable`|Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e restituita al chiamante.|  
|`Reload`|Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.|  
|`NoCacheNoStore`|Se una risorsa memorizzata nella cache esiste, viene eliminata. La risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp è identico a quello della risorsa sul server. In caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
  
## <a name="remarks"></a>Commenti  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un criterio di memorizzazione nella cache FTP di `NoCacheNoStore` .  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Schema delle impostazioni di rete](index.md)
