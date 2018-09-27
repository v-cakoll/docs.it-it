---
title: '&lt;httpWebRequest&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e83f12d849f6f6a587bccc85fbf6fe8fe24026f0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397228"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;httpWebRequest&gt; (impostazioni di rete)
Consente di personalizzare i parametri della richiesta Web.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<httpWebRequest >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte. Il valore predefinito è 64. Il valore -1 indica che non verrà imposto alcun limite di dimensione sulle intestazioni di risposta.|  
|`maximumErrorResponseLength`|Specifica la lunghezza massima di una risposta di errore, in kilobyte. Il valore predefinito è 64. Il valore -1 indica che non verrà imposto alcun limite di dimensione nella risposta di errore.|  
|`maximumUnauthorizedUploadLength`|Specifica la lunghezza massima di un upload in risposta a un codice di errore non autorizzato, in byte. Il valore predefinito è -1. Il valore -1 indica che non verrà imposto alcun limite di dimensione all'upload.|  
|`useUnsafeHeaderParsing`|Specifica se l'analisi dell'intestazione di tipo unsafe è abilitato. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, .NET Framework applica rigorosamente RFC 2616 per l'analisi dell'URI. Alcune risposte server possono includere caratteri di controllo in campi non consentiti, che provoca il <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> metodo consente di generare un <xref:System.Net.WebException>. Se **useUnsafeHeaderParsing** è impostata su **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> non viene generata in questo caso, tuttavia, l'applicazione sarà vulnerabile a diversi strumenti di analisi di attacchi di URI. La soluzione migliore consiste nel modificare il server in modo che la risposta non include i caratteri di controllo.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un maggiore della lunghezza intestazione massima nello stato normale.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
