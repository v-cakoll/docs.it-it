---
title: '&lt;Cancella&gt; (elemento) per bypasslist (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ca6c8e9334bdfcdf4d79c5a91612ee117445d9cb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47237421"
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a>&lt;Cancella&gt; (elemento) per bypasslist (impostazioni di rete)
Cancella l'elenco proxy da ignorare.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy >  
\<BypassList >  
\<clear >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[BypassList](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.|  
  
## <a name="remarks"></a>Note  
 Il `clear` elemento cancella tutte le voci dell'elenco di esclusione.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente cancella l'elenco di esclusione e quindi aggiunge due indirizzi all'elenco di esclusione. Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server il cui indirizzo IP inizia con 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
