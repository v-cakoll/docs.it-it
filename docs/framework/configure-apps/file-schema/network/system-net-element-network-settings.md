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
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154556"
---
# <a name="systemnet-element-network-settings"></a>Elemento \<system.Net> (impostazioni di rete)
Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;**\<>system.net**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Specifica i moduli utilizzati per autenticare le richieste Internet.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a un host Internet.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
|[MailImpostazioni](mailsettings-element-network-settings.md)|Configura le opzioni di invio della posta SMTP (Simple Mail Transport Protocol).|  
|[requestCaching](requestcaching-element-network-settings.md)|Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.|  
|[impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete <xref:System.Net> di base per le classi negli spazi dei nomi figlio correlati e correlati.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Specifica i moduli da utilizzare per richiedere informazioni agli host Internet.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[configurazione](../configuration-element.md)|Contiene le impostazioni per tutti gli spazi dei nomi.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento [ \<system.net>](system-net-element-network-settings.md) contiene <xref:System.Net> le impostazioni per le classi negli spazi dei nomi figlio e correlati. Le impostazioni configurano i moduli di autenticazione, la gestione delle connessioni, le impostazioni di posta, il server proxy e i moduli di richiesta Internet per la ricezione di informazioni dagli host Internet.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una configurazione tipica utilizzata dalle <xref:System.Net> classi.  
  
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
