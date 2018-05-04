---
title: '&lt;requiredRuntime&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 184547dd47e728f17f28105e74b2ca67c1436efc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt; elemento
Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Questo elemento è deprecato e non deve più essere usato. Il [ `supportedRuntime` ](supportedruntime-element.md) elemento da utilizzare in sostituzione.
  
 \<configuration>  
\<startup>  
\<requiredRuntime >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`version`|Attributo facoltativo.<br /><br /> Valore stringa che specifica la versione di .NET Framework supportata dall'applicazione. Il valore di stringa deve corrispondere al nome di directory presente nella directory principale di installazione di .NET Framework. Il contenuto del valore di stringa non viene analizzato.|  
|`safemode`|Attributo facoltativo.<br /><br /> Specifica se il codice di avvio di runtime cerca il Registro di sistema per determinare la versione di runtime.|  
  
## <a name="safemode-attribute"></a>modalità provvisoria attributo  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il codice di avvio di runtime cerca nel Registro di sistema. Rappresenta il valore predefinito.|  
|`true`|Il codice di avvio del runtime non cerca nel Registro di sistema.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`startup`|Contiene il `<requiredRuntime>` elemento.|  
  
## <a name="remarks"></a>Note  
 Nelle applicazioni compilate per supportare esclusivamente la versione 1.0 del runtime è necessario utilizzare il `<requiredRuntime>` elemento. Le applicazioni compilate con la versione 1.1 o successiva del runtime devono utilizzare il `<supportedRuntime>` elemento.  
  
> [!NOTE]
>  Se si utilizza il [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario utilizzare il `<requiredRuntime>` elemento per tutte le versioni del runtime. Il `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 Il `version` stringa dell'attributo deve corrispondere al nome di cartella di installazione per la versione di .NET Framework specificata. Questa stringa non viene interpretata. Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato; il codice di avvio di un messaggio di errore e viene chiusa.  
  
> [!NOTE]
>  Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il `<requiredRuntime>` elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare la versione di runtime in un file di configurazione.  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di avvio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifica della versione di runtime da usare](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
