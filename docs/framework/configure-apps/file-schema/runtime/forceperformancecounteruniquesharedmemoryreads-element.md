---
title: '&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1f041cbfb4195b2c649c3af4fa061bf63e227df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a>&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; elemento
Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se PerfCounter utilizza l'impostazione del Registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni da specifiche della categoria di memoria condivisa o la memoria globale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|PerfCounter non utilizza il CategoryOptions questa impostazione del registro è il valore predefinito.|  
|`true`|PerfCounter utilizzare l'impostazione del Registro di sistema CategoryOptions.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni di .NET Framework prima di [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la versione di PerfCounter che è stato caricato corrispondeva al runtime che è stato caricato nel processo. Se un computer dispone sia a .NET Framework versione 1.1 e [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installato, un'applicazione .NET Framework 1.1 carica la versione di .NET Framework 1.1 di PerfCounter. A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], viene caricata la versione installata più recente di PerfCounter. Ciò significa che un'applicazione .NET Framework 1.1 caricherà il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] versione di PerfCounter. Se il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] è installato nel computer.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], quando si utilizzano i contatori delle prestazioni, PerfCounter controlla la voce del Registro di sistema CategoryOptions per ogni provider per determinare se è necessario leggere dalla memoria condivisa specifiche della categoria o la memoria globale condivisa. Di PerfCounter 1.1 di .NET Framework non legge la voce del Registro di sistema, perché non è compatibile con di memoria condivisa specifiche della categoria. legge sempre dalla memoria condivisa globale.  
  
 Per garantire la compatibilità con le versioni precedenti, il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter non controlla la voce del Registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1.1. Usa semplicemente la memoria globale condivisa, come il PerfCounter 1.1 di .NET Framework. Tuttavia, è possibile indicare il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter per controllare l'impostazione del Registro di sistema, consentendo il `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
>  Abilitazione di `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento non garantisce che verrà utilizzata la memoria condivisa specifiche della categoria. L'impostazione abilitata su `true` solo provoca PerfCounter fare riferimento l'impostazione del Registro di sistema CategoryOptions. L'impostazione predefinita per CategoryOptions consiste nell'utilizzare la memoria condivisa specifiche della categoria. Tuttavia, è possibile modificare CategoryOptions per indicare che la memoria globale condivisa deve essere utilizzata.  
  
 La chiave del Registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance. Per impostazione predefinita, CategoryOptions è impostato su 3, che indica di PerfCounter utilizzare memoria condivisa specifiche della categoria. Se CategoryOptions è impostata su 0, PerfCounter utilizza memoria condivisa globale. Dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza venga riutilizzato. Tutte le versioni sarà in grado di scrivere in tale categoria. Se CategoryOptions è impostato su 1, viene utilizzata la memoria globale condivisa, ma è possibile riutilizzare i dati di istanza se il nome di categoria è uguale alla lunghezza della categoria riutilizzata.  
  
 Le impostazioni di 0 e 1 possono causare perdite di memoria e il riempimento di memoria dei contatori delle prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che PerfCounter devono fare riferimento la voce del Registro di sistema CategoryOptions per determinare se deve utilizzare memoria condivisa specifiche della categoria.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
