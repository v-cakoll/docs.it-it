---
title: Elemento <add> per webRequestModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155024"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>Elemento \<add> per webRequestModules (impostazioni di rete)
Aggiunge un modulo di richiesta Web personalizzato all'applicazione.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`prefix`|Prefisso URI per le richieste gestite da questo modulo di richiesta Web.|  
|`type`|Il nome completo del tipo (indicato dalla <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dalla <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa questo modulo di richiesta Web.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Specifica i moduli da usare per richiedere informazioni dagli host di rete.|  
  
## <a name="remarks"></a>Commenti  
 L' `prefix` attributo definisce il prefisso URI che usa il modulo di richiesta Web specificato. I moduli di richiesta Web vengono in genere registrati per gestire un protocollo specifico, ad esempio HTTP o FTP, ma possono essere registrati per gestire una richiesta a un server o a un percorso specifico in un server.  
  
 Il modulo della richiesta Web viene creato quando un prefisso corrispondente URI viene passato al <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> metodo.  
  
 Il valore dell' `prefix` attributo deve essere costituito dai caratteri iniziali di un URI valido. Ad esempio, `http` o `http://www.contoso.com`.
  
 Il valore dell' `type` attributo deve essere un nome di tipo valido e un nome di assembly corrispondente, separati da una virgola.
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene registrato un modulo di richiesta Web personalizzato per HTTP. È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Net.WebRequest>
- [Schema delle impostazioni di rete](index.md)
