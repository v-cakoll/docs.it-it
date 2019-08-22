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
ms.openlocfilehash: c30a7a0bcce62c99d7c1ec0ff17389b8c2cd2f17
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663936"
---
# <a name="webrequestmodules-element-network-settings"></a>\<Elemento > webRequestModules (impostazioni di rete)
Specifica i moduli da usare per richiedere informazioni dagli host di rete.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
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
  
## <a name="remarks"></a>Note  
 Con l'elemento `webRequestModules` vengono registrati i discendenti della classe <xref:System.Net.WebRequest> per gestire le richieste di informazioni inviate agli host di rete. I moduli di richiesta Web devono <xref:System.Net.IWebRequestCreate> implementare l'interfaccia.  
  
 Il .NET Framework include i moduli di richiesta Web per gli URI `http://`che `https://`iniziano con `file://`, e. È possibile eseguire l'override dei moduli predefiniti solo registrando un modulo personalizzato nel file di configurazione.  
  
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
