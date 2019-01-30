---
title: Elemento <remove> per bypasslist (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: c1e5d9a6726e1ae21d0ab449886b1074e399a655
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256979"
---
# <a name="remove-element-for-bypasslist-network-settings"></a>\<rimuovere > (elemento) per bypasslist (impostazioni di rete)
Rimuove un indirizzo IP o nome DNS dall'elenco di bypass del proxy.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
\<remove>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`address`|Un'espressione regolare che descrive un indirizzo IP o nome DNS.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.|  
  
## <a name="remarks"></a>Note  
 Il `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o nomi di server DNS nell'elenco di indirizzi che ignorano un server proxy. Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.  
  
 Il valore per il `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.  
  
 Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove le definizioni precedenti per il dominio Adventure-Works.com e quindi aggiunge il dominio contoso.com all'elenco di esclusione.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
