---
title: Elemento <proxy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089187"
---
# <a name="proxy-element-network-settings"></a>\<elemento > proxy (impostazioni di rete)
Definisce un server proxy.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy**](defaultproxy-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**proxy** >

## <a name="syntax"></a>Sintassi  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`autoDetect`|Specifica se il proxy viene rilevato automaticamente. Il valore predefinito è `unspecified`.|  
|`bypassonlocal`|Specifica se il proxy viene ignorato per le risorse locali. Le risorse locali includono il server locale (`http://localhost`, `http://loopback`o `http://127.0.0.1`) e un URI senza un punto (`http://webserver`). Il valore predefinito è `unspecified`.|  
|`proxyaddress`|Specifica l'URI del proxy da utilizzare.|  
|`scriptLocation`|Specifica il percorso dello script di configurazione. Non usare l'attributo `bypassonlocal` con questo attributo. |  
|`usesystemdefault`|Specifica se utilizzare le impostazioni proxy di Internet Explorer. Se impostato su `true`, gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer. Il valore predefinito è `unspecified`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="text-value"></a>Valore di testo  
  
## <a name="remarks"></a>Note  
 L'elemento `proxy` definisce un server proxy per un'applicazione. Se questo elemento non è presente nel file di configurazione, il .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.  
  
 Il valore per l'attributo `proxyaddress` deve essere un URI (Uniform Resource Indicator) ben formato.  
  
 L'attributo `scriptLocation` si riferisce al rilevamento automatico degli script di configurazione del proxy. La classe <xref:System.Net.WebProxy> tenterà di individuare uno script di configurazione, in genere denominato wpad. dat, quando si seleziona l'opzione **Usa script di configurazione automatica** in Internet Explorer. Se `bypassonlocal` è impostato su un valore qualsiasi, `scriptLocation` viene ignorato.
  
 Usare l'attributo `usesystemdefault` per le applicazioni .NET Framework versione 1,1 che eseguono la migrazione alla versione 2,0.  
  
 Viene generata un'eccezione se l'attributo `proxyaddress` specifica un proxy predefinito non valido. La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
