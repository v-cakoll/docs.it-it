---
title: Elemento <requestCaching> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802123"
---
# <a name="requestcaching-element-network-settings"></a>Elemento \<requestCaching> (impostazioni di rete)
Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<requestCaching >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`isPrivateCache`|Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi. Il valore predefinito è `true`. Questo valore deve essere `false` per le applicazioni di livello intermedio.|  
|`disableAllCaching`|Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposta a override a livello di codice.|  
|`defaultPolicyLevel`|Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>. Il valore predefinito è `BypassCache`.|  
|`unspecifiedMaximumAge`|Specifica l'ora predefinita dopo la quale il contenuto è contrassegnato come scaduto.|  
  
## <a name="policylevel-attribute"></a>policyLevel (attributo)  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`Default`|Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.|  
|`BypassCache`|Restituisce la risorsa dal server.|  
|`CacheOnly`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.|  
|`CacheIfAvailable`|Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e viene restituita al chiamante.|  
|`Reload`|Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.|  
|`NoCacheNoStore`|Se una risorsa memorizzata nella cache esiste, viene eliminata. La risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](defaulthttpcachepolicy-element-network-settings.md)|Elemento facoltativo.<br /><br /> Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.|  
|[\<elemento > defaultFtpCachePolicy (impostazioni di rete)](defaultftpcachepolicy-element-network-settings.md)|Elemento facoltativo.<br /><br /> Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare tutti i Caching.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
