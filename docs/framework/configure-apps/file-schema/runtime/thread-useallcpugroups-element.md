---
title: '&lt;Thread_UseAllCpuGroups&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c574d6f5598616776e891ab282c703ce20bc6960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltthreaduseallcpugroupsgt-element"></a>&lt;Thread_UseAllCpuGroups&gt; elemento
Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.  
  
 \<configuration>  
\<runtime >  
<Thread_UseAllCpuGroups>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il runtime non distribuisce i thread gestiti in più gruppi di CPU. Questa è l'impostazione predefinita.|  
|`true`|Il runtime distribuisce i thread gestiti in più gruppi di CPU, se il computer dispone di più gruppi di CPU e [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento è abilitato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando un computer dispone di più gruppi di CPU, abilitazione di questo elemento, il runtime di distribuire i thread gestiti in tutti i gruppi di CPU. Per utilizzare questa funzionalità, è necessario abilitare il [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento, che estende l'operazione di garbage collection a tutti i gruppi di CPU e tiene conto durante la creazione e bilanciamento degli heap di tutti i core. Abilitazione di [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento richiede l'abilitazione di [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento. Se questi elementi non sono abilitati, l'abilitazione di `<Thread_UseAllCpuGroups>` elemento non ha alcun effetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<GCCpuGroup > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
