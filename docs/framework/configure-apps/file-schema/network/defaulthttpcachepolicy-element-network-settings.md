---
title: Elemento <defaultHttpCachePolicy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 20d9b92ca2bbffd6b98b8641e5cef5e567cb84cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705129"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>\<defaultHttpCachePolicy > (impostazioni di rete)
Indica se la memorizzazione nella cache HTTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
\<defaultHttpCachePolicy>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maximumAge`|Specifica l'intervallo di tempo massimo prima che un oggetto memorizzato nella cache viene contrassegnato come scaduto.|  
|`maximumStale`|Specifica il tempo massimo oltre il tempo di validità calcolato prima che un oggetto memorizzato nella cache viene contrassegnato come scaduto.|  
|`minimumFresh`|Specifica il tempo minimo per un oggetto memorizzato nella cache essere considerato aggiornato.|  
|`policyLevel`|Specifica se i criteri di memorizzazione nella cache sono automatica, o se la cache viene ignorata. Il valore predefinito è `BypassCache`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
  
## <a name="remarks"></a>Note  
 Il valore per il `policyLevel` attributo è uno `BypassCache` o `Default`.  
  
 I valori per il `maximumAge`, `maximumStale`, e `minimumFresh` elementi sono da un intervallo di tempo esplicito con il formato *1!d*. *hh*:*mm*:*ss* (giorni, ore, minuti e secondi), o le costanti `minValue` o `maxValue`, nel modo appropriato.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un tempo minimo fresco di sei ore, un intervallo di durata massima di due giorni e un intervallo di obsolescenza massima pari a quattro ore.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
