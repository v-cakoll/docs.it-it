---
title: Elemento <clear> per bypasslist (impostazioni di rete)
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
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154933"
---
# <a name="clear-element-for-bypasslist-network-settings"></a>\<clear> elemento per bypasslist (impostazioni di rete)
Cancella l'elenco di esclusione proxy.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>defaultProxy**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<elenco di>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>chiari**

## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[elenco di bypass](bypasslist-element-network-settings.md)|Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `clear` cancella tutte le voci dall'elenco di esclusione.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cancellato l'elenco di esclusione e quindi vengono aggiunti due indirizzi all'elenco di esclusione. Il primo ignora il proxy per tutti i server nel dominio contoso.com; il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192.168.  
  
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

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
