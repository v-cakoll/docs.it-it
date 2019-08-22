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
ms.openlocfilehash: 1dd31884a072d16ed004c0b49be61e8cee399787
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664147"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>\<Elemento > defaultHttpCachePolicy (impostazioni di rete)
Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.  
  
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
|`maximumAge`|Specifica l'intervallo di tempo massimo prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.|  
|`maximumStale`|Specifica il tempo massimo trascorso il tempo di aggiornamento calcolato prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.|  
|`minimumFresh`|Specifica il tempo minimo per considerare aggiornato un oggetto memorizzato nella cache.|  
|`policyLevel`|Specifica se i criteri di memorizzazione nella cache sono automatici o se la cache è stata ignorata. Il valore predefinito è `BypassCache`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
  
## <a name="remarks"></a>Note  
 Il valore `policyLevel` dell'attributo `BypassCache` è o `Default`.  
  
 I valori per `maximumAge`gli `maximumStale`elementi, `minimumFresh` e sono un intervallo di tempo esplicito con un formato *d*. *HH*:*mm*:*SS* (giorni, ore, minuti e secondi) `minValue` o costanti o `maxValue`, a seconda dei casi.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un periodo di tempo minimo di sei ore, una durata massima di due giorni e un tempo di esecuzione massimo di quattro ore.  
  
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
- [Schema delle impostazioni di rete](index.md)
