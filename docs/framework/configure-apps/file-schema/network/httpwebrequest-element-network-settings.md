---
title: Elemento <httpWebRequest> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: fa00aed2cd1e96ec788d4bc9c1c63f20561d8d1c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698177"
---
# <a name="httpwebrequest-element-network-settings"></a>Elemento > \<httpWebRequest (impostazioni di rete)
Personalizza i parametri della richiesta Web.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpWebRequest >**  
  
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
  
|**Attribute**|**Descrizione**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte. Il valore predefinito è 64. Il valore-1 indica che non verrà imposto alcun limite di dimensioni per le intestazioni della risposta.|  
|`maximumErrorResponseLength`|Specifica la lunghezza massima di una risposta di errore, espressa in kilobyte. Il valore predefinito è 64. Il valore-1 indica che non verrà imposto alcun limite di dimensioni per la risposta di errore.|  
|`maximumUnauthorizedUploadLength`|Specifica la lunghezza massima di un caricamento in risposta a un codice di errore non autorizzato, in byte. Il valore predefinito è -1. Il valore-1 indica che non verrà imposto alcun limite di dimensioni per il caricamento.|  
|`useUnsafeHeaderParsing`|Specifica se è abilitata l'analisi dell'intestazione unsafe. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il .NET Framework impone rigorosamente RFC 2616 per l'analisi dell'URI. Alcune risposte al server possono includere caratteri di controllo in campi non consentiti, che determinano la generazione di un <xref:System.Net.WebException> da parte del metodo <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>. Se **UseUnsafeHeaderParsing** è impostato su **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> non genererà in questo caso. Tuttavia, l'applicazione sarà vulnerabile a diverse forme di attacchi di analisi URI. La soluzione migliore consiste nel modificare il server in modo che la risposta non includa i caratteri di controllo.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare una lunghezza massima di intestazione maggiore di quella normale.  
  
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

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [Schema delle impostazioni di rete](index.md)
