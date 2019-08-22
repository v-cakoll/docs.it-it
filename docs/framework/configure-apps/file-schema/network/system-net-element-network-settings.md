---
title: Elemento <system.Net> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 449146612938700f59f5e2ec761526d1dc66a3fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663953"
---
# <a name="systemnet-element-network-settings"></a>Elemento \<system.Net> (impostazioni di rete)
Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.  
  
 \<configuration>  
\<system.net>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Specifica i moduli usati per autenticare le richieste Internet.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a un host Internet.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
|[mailSettings](mailsettings-element-network-settings.md)|Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).|  
|[requestCaching](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per le <xref:System.Net> classi in e gli spazi dei nomi figlio correlati.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Specifica i moduli da usare per richiedere informazioni da host Internet.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Contiene le impostazioni per tutti gli spazi dei nomi.|  
  
## <a name="remarks"></a>Note  
 <xref:System.Net> L' [ \<elemento System. net >](system-net-element-network-settings.md) contiene le impostazioni per le classi in e gli spazi dei nomi figlio correlati. Le impostazioni configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una configurazione tipica <xref:System.Net> utilizzata dalle classi.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di rete](index.md)
