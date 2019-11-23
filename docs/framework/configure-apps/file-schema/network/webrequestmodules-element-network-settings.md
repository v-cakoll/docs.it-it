---
title: Elemento <webRequestModules> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697469"
---
# <a name="webrequestmodules-element-network-settings"></a>\<elemento > webRequestModules (impostazioni di rete)
Specifica i moduli da usare per richiedere informazioni dagli host di rete.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|Aggiunge un modulo di richiesta Web personalizzato all'applicazione.|  
|[clear](clear-element-for-webrequestmodules-network-settings.md)|Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.|  
|[remove](remove-element-for-webrequestmodules-network-settings.md)|Rimuove un modulo di richiesta Web personalizzato dall'applicazione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="remarks"></a>Osservazioni  
 Con l'elemento `webRequestModules` vengono registrati i discendenti della classe <xref:System.Net.WebRequest> per gestire le richieste di informazioni inviate agli host di rete. I moduli di richiesta Web devono implementare l'interfaccia <xref:System.Net.IWebRequestCreate>.  
  
 Il .NET Framework include moduli di richiesta Web per gli URI che iniziano con `http://`, `https://`e `file://`. È possibile eseguire l'override dei moduli predefiniti solo registrando un modulo personalizzato nel file di configurazione.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene registrato il modulo HTTP predefinito. È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Schema delle impostazioni di rete](index.md)
