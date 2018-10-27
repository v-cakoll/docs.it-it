---
title: '&lt;aggiungere&gt; (elemento) per webRequestModules (impostazioni di rete)'
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
ms.openlocfilehash: 4c823f366baf51b35c15a87c2a9f6c9c4d3102d0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188535"
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a>&lt;aggiungere&gt; (elemento) per webRequestModules (impostazioni di rete)
Aggiunge un modulo di richiesta Web personalizzato per l'applicazione.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules >  
\<add>  
  
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
|`prefix`|Il prefisso URI per le richieste gestite da questo modulo di richiesta Web.|  
|`type`|Il nome completo del tipo (indicato dal <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dal <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa questo modulo di richiesta Web.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Specifica i moduli da utilizzare per richiedere informazioni da host di rete.|  
  
## <a name="remarks"></a>Note  
 Il `prefix` attributo definisce il prefisso URI che usa il modulo di richiesta Web specificato. Moduli di richiesta Web sono in genere registrati per gestire un protocollo specifico, ad esempio HTTP o FTP, ma possono essere registrati per gestire una richiesta a un server specifico o un percorso in un server.  
  
 Il modulo di richiesta Web viene creato quando viene passato un prefisso corrispondente a un URI per il <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> (metodo).  
  
 Il valore per il `prefix` attributo deve corrispondere ai caratteri iniziali di un URI valido. Ad esempio, `http` o `http://www.contoso.com`.
  
 Il valore per il `type` attributo deve essere un nome di tipo valido e il corrispondente nome dell'assembly, separati da una virgola.
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente registra un modulo di richiesta Web personalizzato per il protocollo HTTP. È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.  
  
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
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
