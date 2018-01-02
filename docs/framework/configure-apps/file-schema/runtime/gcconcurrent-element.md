---
title: '&lt;gcConcurrent&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 254b3be8f270a9186377b264094c919314efb27f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcConcurrent&gt; elemento
Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.  
  
 \<configuration>  
\<runtime >  
\<gcConcurrent >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|La procedura di Garbage Collection non viene eseguita in modo concorrente.|  
|`true`|Viene eseguita la procedura di Garbage Collection in modo concorrente. Questa è l'impostazione predefinita.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Prima di .NET Framework 4, la Garbage Collection per workstation supportava la Garbage Collection in modalità simultanea, che eseguiva la Garbage Collection in background in un thread separato. A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è stata sostituita dalla modalità in background, che esegue anch'essa la Garbage Collection in background in un thread separato. A partire da .NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile anche per server. L'elemento `<gcConcurrent>` controlla se il runtime esegue la Garbage Collection simultanea o in background, se è disponibile o se esegue la Garbage Collection in primo piano.  
  
> [!WARNING]
>  A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è sostituita dalla Garbage Collection in background. Le condizioni di *simultanee* e *background* vengono usati indifferentemente nella documentazione di .NET Framework. Per disabilitare il Garbage Collection in background, usare l'elemento `<gcConcurrent>`, come illustrato in questo articolo.  
  
 Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza. Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection. Se si imposta l'attributo `enabled` dell'elemento `<gcConcurrent>` su `false`, da parte del runtime viene usata la Garbage Collection in modalità non simultanea, ottimizzata per la velocità effettiva. Il file di configurazione seguente disabilita la Garbage Collection in background.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Se esiste un'impostazone `<gcConcurrentSetting>` nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework. Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.  
  
 Per ulteriori informazioni su simultanee e garbage collection in background, vedere la sezione "garbage collection contemporanea" nel [principi fondamentali di Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) argomento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente abilita la Garbage Collection in modalità simultanea.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Principi fondamentali di Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md)
