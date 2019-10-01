---
title: Elemento <bypasslist> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 1dda43be8c0e0c94bdf7b57b67aa4d403b547f97
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699547"
---
# <a name="bypasslist-element-network-settings"></a>Elemento > \<bypasslist (impostazioni di rete)
Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<bypasslist >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](add-element-for-bypasslist-network-settings.md)|Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.|  
|[clear](clear-element-for-bypasslist-network-settings.md)|Cancella l'elenco di bypass.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="remarks"></a>Note  
 L'elenco di bypass contiene espressioni regolari che descrivono gli URI che <xref:System.Net.WebRequest> istanze di accedono direttamente anziché tramite il server proxy.  
  
 È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento. L'espressione regolare "[a-z] + @no__t -0.contoso\\.com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com. Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] + @no__t -0.contoso\\.com $".  
  
 Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass. Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server i cui indirizzi IP iniziano con 192,168.  
  
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
- [Schema delle impostazioni di rete](index.md)
