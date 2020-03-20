---
title: Elemento <remove> per webRequestModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154725"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<rimuovere>elemento per webRequestModules (impostazioni di rete)
Rimuove un modulo di richiesta Web personalizzato dall'applicazione.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>webRequestModules**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rimuovere>**
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`prefix`|Prefisso URI per le richieste gestite da questo modulo di richiesta Web.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Specifica i moduli da utilizzare per richiedere informazioni agli host di rete.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `remove` rimuove il modulo di richiesta Web registrato per il prefisso URI specificato.  
  
 Il valore `prefix` dell'attributo deve essere costituito dai caratteri`http`iniziali di`http://www.contoso.com`un URI valido, ad esempio " " o " ".  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  

Nell'esempio riportato di seguito viene rimosso il modulo di richiesta Web `www.contoso.com`esistente per HTTP, quindi viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP in .
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebRequest>
- [Schema delle impostazioni di rete](index.md)
