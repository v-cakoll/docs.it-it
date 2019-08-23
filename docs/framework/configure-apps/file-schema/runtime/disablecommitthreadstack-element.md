---
title: <disableCommitThreadStack> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3071b25392048161ebb40c39842f5da0dce3475
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920836"
---
# <a name="disablecommitthreadstack-element"></a>\<Elemento > disableCommitThreadStack
Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.  
  
 \<configuration>  
\<runtime>  
\<disableCommitThreadStack>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se il commit dello stack di thread completo all'avvio del thread (comportamento predefinito) è disabilitato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Non disabilitare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.|  
|1|Disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Il comportamento predefinito del Common Language Runtime è eseguire il commit dello stack di thread completo quando viene avviato un thread. Se un numero elevato di thread deve essere creato in un server con memoria limitata e la maggior parte dei thread utilizzerà pochissimo spazio dello stack, il server potrebbe avere prestazioni migliori se il Common Language Runtime non esegue il commit dello stack di thread completo immediatamente quando viene avviato un thread.  
  
> [!NOTE]
> Gli host non gestiti possono usare il flag di avvio `STARTUP_DISABLE_COMMITTHREADSTACK` nell'enumerazione [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) per ottenere lo stesso risultato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo all'avvio del thread.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
