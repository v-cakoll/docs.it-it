---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: efa6dce1035f7d2cf63b74c6a03d911b5dede722
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116957"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<elemento > forcePerformanceCounterUniqueSharedMemoryReads
Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<forcePerformanceCounterUniqueSharedMemoryReads >**  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se PerfCounter. dll usa l'impostazione del registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|PerfCounter. dll non usa l'impostazione predefinita del registro di sistema CategoryOptions.|  
|`true`|PerfCounter. dll usa l'impostazione del registro di sistema CategoryOptions.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni del .NET Framework prima del .NET Framework 4, la versione di PerfCounter. dll che è stata caricata corrisponde al runtime caricato nel processo. Se un computer ha installato sia la versione di .NET Framework 1,1 che la .NET Framework 2,0, un'applicazione .NET Framework 1,1 caricherà la versione .NET Framework 1,1 di PerfCounter. dll. A partire da .NET Framework 4, viene caricata la versione installata più recente di PerfCounter. dll. Ciò significa che un'applicazione .NET Framework 1,1 caricherà la versione .NET Framework 4 di PerfCounter. dll se il .NET Framework 4 è installato nel computer.  
  
 A partire da .NET Framework 4, quando si utilizzano i contatori delle prestazioni, PerfCounter. dll controlla la voce del registro di sistema CategoryOptions per ogni provider per determinare se deve essere letta dalla memoria condivisa specifica della categoria o dalla memoria condivisa globale. Il .NET Framework 1,1 PerfCounter. dll non legge la voce del registro di sistema perché non è in grado di riconoscere la memoria condivisa specifica della categoria; viene sempre letta dalla memoria condivisa globale.  
  
 Per compatibilità con le versioni precedenti, il .NET Framework 4 PerfCounter. dll non controlla la voce del registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1,1. Usa semplicemente la memoria condivisa globale, proprio come la .NET Framework 1,1 PerfCounter. dll. Tuttavia, è possibile indicare al .NET Framework 4 PerfCounter. dll di controllare l'impostazione del registro di sistema abilitando l'elemento `<forcePerformanceCounterUniqueSharedMemoryReads>`.  
  
> [!NOTE]
> L'abilitazione dell'elemento `<forcePerformanceCounterUniqueSharedMemoryReads>` non garantisce che venga utilizzata la memoria condivisa specifica della categoria. Se si imposta Enabled su `true`, PerfCounter. dll fa riferimento solo all'impostazione del registro di sistema CategoryOptions. L'impostazione predefinita per CategoryOptions consiste nell'usare la memoria condivisa specifica della categoria; Tuttavia, è possibile modificare CategoryOptions per indicare che deve essere utilizzata la memoria condivisa globale.  
  
 La chiave del registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< CategoryName\>\Performance. Per impostazione predefinita, CategoryOptions è impostato su 3, che indica a PerfCounter. dll di usare la memoria condivisa specifica della categoria. Se CategoryOptions è impostato su 0, PerfCounter. dll utilizza la memoria condivisa globale. I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza in fase di riutilizzo. Tutte le versioni saranno in grado di scrivere nella categoria. Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria ha la stessa lunghezza della categoria riutilizzata.  
  
 Le impostazioni 0 e 1 possono causare perdite di memoria e la compilazione della memoria del contatore delle prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che PerfCounter. dll deve fare riferimento alla voce del registro di sistema CategoryOptions per determinare se deve utilizzare la memoria condivisa specifica della categoria.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
