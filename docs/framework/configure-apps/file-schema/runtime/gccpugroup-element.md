---
title: '&lt;GCCpuGroup&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ab18cded2b9a16fe2520547287198d3cfe6b74
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529311"
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; elemento
Specifica se Garbage Collection supporta più gruppi di CPU.  
  
 \<configuration>  
\<runtime>  
\<GCCpuGroup>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se Garbage Collection supporta più gruppi di CPU.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Operazione di Garbage collection non supporta più gruppi di CPU. Questa è l'impostazione predefinita.|  
|`true`|Operazione di Garbage collection supporta più gruppi di CPU, se garbage collection per server è abilitato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando un computer con più gruppi di CPU, garbage collection per server è abilitata (vedere la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento), abilitazione di questo elemento consente di estendere la garbage collection in tutti i gruppi di CPU e accetta tutte le memorie centrali in account durante la creazione e bilanciamento degli heap.  
  
> [!NOTE]
>  Questo elemento si applica solo ai thread di garbage collection. Per abilitare il runtime distribuisca i thread utente in tutti i gruppi di CPU, è necessario abilitare anche il [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare la procedura di garbage collection per più gruppi di CPU.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Procedura: disabilitare la Garbage Collection simultanea](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [Operazione di garbage collection workstation e server](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
