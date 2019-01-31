---
title: Elemento <bypasslist> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: db975d44db96f605767d7320737ff3c162bbc8a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282958"
---
# <a name="bypasslist-element-network-settings"></a>\<BypassList > (impostazioni di rete)
Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Aggiunge un indirizzo IP o nome DNS per l'elenco proxy da ignorare.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Cancella l'elenco di esclusione.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Rimuove un indirizzo IP o nome DNS dall'elenco di bypass del proxy.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="remarks"></a>Note  
 Elenco di esclusione contiene espressioni regolari che descrivono gli URI che <xref:System.Net.WebRequest> istanze accedere direttamente anziché tramite il server proxy.  
  
 È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento. L'espressione regolare "[a-z] +\\.contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, che corrisponde anche a qualsiasi host nel dominio cpandl.com. In modo che corrisponda solo un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] +\\.contoso\\$. com".  
  
 Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge due indirizzi all'elenco di esclusione. Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server iniziano con indirizzi IP 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
