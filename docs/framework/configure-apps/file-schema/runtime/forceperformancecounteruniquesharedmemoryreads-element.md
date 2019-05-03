---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d4a205f643c844b2fe77d3aa5211b4bc1f322fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674254"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads > elemento
Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads>  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se PerfCounter. dll Usa l'impostazione del Registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni di memoria condivisa specifica della categoria o della memoria globale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|PerfCounter non usa il CategoryOptions questa impostazione del registro è il valore predefinito.|  
|`true`|PerfCounter usare l'impostazione del Registro di sistema CategoryOptions.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni di .NET Framework antecedenti il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la versione di PerfCounter. dll è stato caricato corrispondeva al runtime che è stato caricato nel processo. Se un computer dispone sia a .NET Framework versione 1.1 e [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installata, un'applicazione .NET Framework 1.1 carica la versione di .NET Framework 1.1 di PerfCounter. dll. A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], viene caricata la versione installata più recente di PerfCounter. dll. Ciò significa che un'applicazione .NET Framework 1.1 verrà caricato il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] versione di PerfCounter. Se il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] è installato nel computer.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], quando si utilizzano contatori delle prestazioni, PerfCounter controlla la voce del Registro di sistema CategoryOptions per ogni provider determinare se è necessario leggere dalla memoria condivisa specifica della categoria o la memoria condivisa globale. Il .NET Framework 1.1 PerfCounter. dll non legge tale voce del Registro di sistema, perché non è conoscenza di memoria condivisa specifiche della categoria. legge sempre dalla memoria condivisa globale.  
  
 Per garantire la compatibilità con le versioni precedenti, il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter non verifica la voce del Registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1.1. Utilizza semplicemente memoria condivisa globale, esattamente come il .NET Framework 1.1 PerfCounter. dll. Può però istruire il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter. dll per verificare l'impostazione del Registro di sistema, consentendo la `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
>  L'abilitazione di `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento non garantisce che verrà utilizzata la memoria condivisa specifiche della categoria. Impostazione abilitata a `true` fa sì che solo fare riferimento l'impostazione del Registro di sistema CategoryOptions PerfCounter. dll. L'impostazione predefinita per CategoryOptions consiste nell'usare specifiche della categoria memoria condivisa. Tuttavia, è possibile modificare CategoryOptions per indicare che la memoria condivisa globale deve essere utilizzata.  
  
 La chiave del Registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance. Per impostazione predefinita, CategoryOptions è impostato su 3, che indica di PerfCounter. dll da utilizzare memoria condivisa specifica della categoria. Se CategoryOptions è impostato su 0, PerfCounter utilizza memoria condivisa globale. I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza vengono riutilizzato. Tutte le versioni sarà in grado di scrivere in tale categoria. Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria è uguale alla lunghezza della categoria verrà riutilizzata.  
  
 Le impostazioni di 0 e 1 possono causare perdite di memoria e il riempimento del memoria dei contatori delle prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che PerfCounter devono fare riferimento la voce del Registro di sistema CategoryOptions per determinare se deve utilizzare memoria condivisa specifica della categoria.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
